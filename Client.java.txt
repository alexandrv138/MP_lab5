package Proxy;

import java.io.File;

public class Client {
    public static void main(String []args){
        File file = new File("C:\\Users\\Acer1212\\Desktop\\who.txt");
        if(file.exists()){
            file.delete();
        }
        User manager = new User("Adam","OK");
        Folder managerProxy = new FolderProxyImpl(manager);
        managerProxy.show("C:\\Users\\Acer1212\\Desktop\\weather.txt");

        User manager2 = new User("Nil","OK");
        Folder managerProxy2 = new FolderProxyImpl(manager2);
        managerProxy2.show("C:\\Users\\Acer1212\\Desktop\\weather.txt");

        System.out.println("_______________");

        User developer = new User("Kris","Wrong");
        FolderProxyImpl developerWrong = new FolderProxyImpl(developer);
        developerWrong.show("My wrong path");
    }
}