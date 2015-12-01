CreditScoreUI.hpp :

#ifndef CreditScoreUI_hpp
#define CreditScoreUI_hpp
  class CreditScoreUI
 {
    public:
    CreditScoreBean EnterDetails();
  };
#endif


CreditScoreUI.cpp :

#include"CreditScoreUI.hpp"
#include<iostream>
CreditScoreBean bean;
int ssn,pid;
CreditScoreBean CreditScoreUI :: EnterDetails()
{
cout<<"Enter Your ssn";
cin>>ssn;
cout<<"Enter the policy id";
cin>>pid;
bean.setssn(ssn);
bean.setpid(pid);
return bean;
}



CreditScoreBean.hpp :

#ifndef CreditScoreBean_hpp
#define CreditScoreBean_hpp
  class CreditScoreBean
 {
    public:
    void setssn(int);
    void setpid(int);
    int getssn(void);
   int getpid(void);
  };
#endif



CreditScoreBean.cpp :

#include"CreditScoreBean.hpp"
#include<iostream>
int l_ssn,l_pid;
void CreditScoreBean:: setssn(int ssn)
{
  l_ssn = ssn;
}
void CreditScoreBean::setpid(int pid)
{
 l_pid = pid;
}
void CreditScoreBean::getpid(void)
{
 return pid;
}
void CreditScoreBean::getscore(void)
{
 return score;
}




CreditScoreController.hpp :

#ifndef CreditScoreController_hpp
#define CreditScoreController_hpp
  class CreditScoreController
 {
    public:
  void initiateCreditScoreCalculation(void);
};
#endif



CreditScoreController.cpp :

#include"CreditScoreController.hpp"
#include"CreditScoreController.hpp"
#include<iostream>
CreditScoreBean bean;
CreditScoreUI view;
CreditScore md;
int score;
void CreditScoreController :: initiateCreditScoreController(void)
{
  bean = view.EnterDetails();
  score = md.CalcScore(bean);
}

CreditScore.hpp :

#ifndef CreditScore_hpp
#define CreditScore_hpp
  class CreditScore
 {
    public:
  int CalcScore(CreditScoreBean);
};
#endif



CreditScore.cpp :

#include"CreditScore.hpp"
#include<iostream>
int l_ssn,l_pid;
int CreditScore::CalcScore(CreditScoreBean bean)
{
l_ssn = bean.getssn();
l_pid = bean.getpid();

}


