# sunhuawen
#
include <string>
using namespace std;

class Book
{
private:
	string Book_name; //书名
	string Book_num;  //条形码
	int Sum;  //馆藏数量
public:
	Book();
	string Get_BName(); //返回书名
	string Get_BNum();  //返回条形码
	int Get_Sum();    //返回馆藏容量
	void Set_BName(string name);  //设置书名
	void Set_BNum(string num);   //设置条形码
	void Set_BSum(int sum);  //设置存量
	bool Bro_Book();   //被借
	void Re_Book();   //被还
	void Add_Book(int num); //添加该书的总量
	Book &operator = (const Book &book); //重载=运算符
};

#define BOOK_MAX_SUM 100  //书库可存储的书的种类的上限

class Book_DBase
{
public:
	unsigned int max_sum;  //书的总类上限
	unsigned int cur_sum;  //当前书的总类
	Book *books; //书库
public:
	Book_DBase();
	bool Search_Book(string name,Book &book,int &pos);  //在书库中搜索指定书名的书籍
	bool Add_Book(string name,Book book);  //添加书籍
	bool Del_Book(string name,Book &book);  //删除书籍
	bool Init_BookDabse();  //初始化书库
	void Write_into_file();  //将书库信息写入文件
	void Update_Info_Book(Book book); //跟新书库中指定书的信息
};
