package Proxy;

import java.io.*;

public class FolderProxyImpl implements Folder {
    private FolderImpl folder;
    private User user;

    public FolderProxyImpl(User user){
        this.user = user;
    }

    public User getUser(){
        return this.user;
    }

    @Override
    public void show(String path) {
        if(user.getAccess() != null && user.getAccess().equals("OK")){
            folder = new FolderImpl();
            try {
                RandomAccessFile writer = new RandomAccessFile("C:\\Users\\Acer1212\\Desktop\\who.txt","rw");
                writer.seek(writer.length());
                writer.writeBytes("User: "+this.getUser().getUserName()+"   Access: "+this.getUser().getAccess()+"  \r\n");
                writer.close();
                System.out.println("User: "+this.getUser().getUserName()+"   Access: "+this.getUser().getAccess());
            } catch (IOException e) {
                e.printStackTrace();
            }
            folder.show(path);
        } else {
            System.out.println(this.getUser().getUserName() + "     Don't have access!");
        }
    }
}