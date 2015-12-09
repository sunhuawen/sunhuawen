# sunhuawen

class Login

{

public:

	string Zhang_Hao;  //帐号
	string Mi_Ma;   //密码
public:

	Login()
	{
		Zhang_Hao="";
		Mi_Ma="";
	}
	Login(string zh,string mi)
	{
		Zhang_Hao=zh;
		Mi_Ma=mi;
	}
};

class CCenterClass  

{

public:

	CCenterClass();
	virtual ~CCenterClass();
public:

	Book_DBase BDase;
	Reader_DBase RDase;
	int zh_sum; //当前账户总数
	Login *login;
	Reader Mian_Reader;
public:

	void INit_Login(); //初始化账户
	bool Update_login_file();//更新文件中的账户信息
	bool Update_Mima(string Zhanghao,string mima); //更新账户类的信息
	bool Search_the_ZH(string zhanghao,int &pos); //在账户类中搜索帐号，并保存其位置
	bool Search_the_MM(int pos,string mima);	//密码匹配
	bool Add_login(Login login);//增加账户
};

