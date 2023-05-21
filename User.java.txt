package Proxy;

public class User {
    private String userName;
    private String access;

    public User(String userName,String access){
        this.userName = userName;
        this.access = access;
    }

    public void setUserName(String userName){
        this.userName = userName;
    }
    public String getUserName(){
        return this.userName;
    }
    public void setAccess(String access){
        this.access = access;
    }
    public String getAccess(){
        return this.access;
    }
}
