# oop2-java-labs
#assignments not in continuous form

##lab 1
#exemption handling
#using java

package exceptionpractice;

import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;


public class ExceptionPractice {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        try{
                System.out.println("Reading from file:" + args[0]); 
            }catch(ArrayIndexOutOfBoundsException e){
            System.out.println("No file specified, quitting!");
         System.exit(1);
            }
        try ( BufferedReader b =
                new BufferedReader(new FileReader(args[0]));) {
            String s = null;
            while((s = b.readLine()) != null) {
            System.out.println(s);
            }
       } catch(FileNotFoundException e) {
            System.out.println("File not found:" + args[0]);
            System.exit(1);
       } catch(IOException e) {
            System.out.println("Error reading file:" + e.getMessage());
            System.exit(1);
       } 
    }
}
