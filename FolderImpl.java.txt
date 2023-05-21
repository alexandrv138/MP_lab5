package Proxy;

import java.io.FileReader;
import java.io.IOException;

public class FolderImpl implements Folder {
    @Override
    public void show(String path) {
        try {
            FileReader reader = new FileReader(path);
            int symbol = 0;
            System.out.print("Text:     ");
            while(symbol != -1){
                System.out.print((char) symbol);
                symbol = reader.read();
            }
            System.out.println("");
            reader.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
