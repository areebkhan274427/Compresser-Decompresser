
# File Compressor and Decompressor
The main objective of this File Compression project is to design a compression GUI which significantly reduces the size of a file so that it can be easily shared over mail even in slow internet speed. This GUI works in the same way as the winrar and winzip, which are popular compression tools. Each byte of the file will be compressed and takes quite less memory on the disk.In this project

Made a GUI to compress a txt file into a gzip file and decode the encoded text file (compressed into gzip
file). 

Was able to compress a file of size 1.97GB to 5.45MB.

Used java awt and java swing to design a GUI.
# Video Demo
[File.webm](https://user-images.githubusercontent.com/74968170/196523890-b371829a-8553-41fc-ad88-b2666d5e66f1.webm)

<!-- https://user-images.githubusercontent.com/74968170/196412431-26733d97-5a90-449f-8e1e-2f069eab5fce.mp4 -->

# Details of Projects 
basically there is a two part of project where in one part we are basically compressing a file and another part again decompressing again.
# Compress java :

              public class Compress {
                 public static void method(File file) throws IOException{
                  String fileDirectory =file.getParent();
                  System.out.println(fileDirectory);
                  FileInputStream fis = new FileInputStream(file);
                  FileOutputStream fos = new FileOutputStream(fileDirectory + "/Comptreddedfile.gz");
                  GZIPOutputStream gzipOS = new GZIPOutputStream(fos);
                  byte []buffer = new byte[1024];

                  int len;
                  while((len=fis.read(buffer)) !=-1){
                      gzipOS.write(buffer,0,len);
                  }
              gzipOS.close();
              fos.close();
              fis.close();
                 } 
                 public static void main(String [] args)throws IOException{
                     File path=new File("C:\\Users\\arvin\\OneDrive\\Desktop\\resume\\text.txt");
                     method(path);
                 }
              }

here we are using FileInputStream() to take a input stream and FileOutputStream for saving the files with same parents directry . GZIPOutputStream gzipOS = new GZIPOutputStream(fos) this is the main method which will giving the compress file in the form of objecs.we are also making buffer array to compress line by line each word according to our requirments ,we are taking a input txt file in main method and passed the method to compress.
# Decompress .java 

              public class Decompress {

                  /**
                   *
                   * @param args
                   * @throws IOException
                   */
                  public static void method(File file) throws IOException{
                      String fileDirectory = file.getParent();
                      System.out.println(fileDirectory);
                      FileInputStream fis= new FileInputStream(file);
                      FileOutputStream fos = new FileOutputStream(fileDirectory +"/Dicompress.txt");
                      GZIPInputStream gis = new GZIPInputStream(fis);

                      byte []buffer = new byte[1024];
                      int len=0;

                      while((len=gis.read(buffer))!=-1){
                          fos.write(buffer,0,len);
                      }
                      gis.close();
                      fis.close();
                      fos.close();
              //        
                  }



                  public static void main(String[] args) throws IOException {
                   File file = new File("C:\\Users\\arvin\\OneDrive\\Desktop\\resume\\Comptreddedfile.gz");  
                   method(file);
                  }
              }
 
Here the function is almost similar to compressor in reverse order..

# file comperssed
![ScreenShot Tool -20221019011535](https://user-images.githubusercontent.com/74968170/196529167-64dd1dcc-d83f-47da-b860-624befe3b5d0.png)


# Java Swing and awt
AWT and Swing are used to develop window-based applications in Java. Awt is an abstract window toolkit that provides various component classes like Label, Button, TextField, etc., to show window components on the screen. All these classes are part of the Java.awt package.

On the other hand, Swing is the part of JFC (Java Foundation Classes) built on the top of AWT and written entirely in Java
. The javax.swing API provides all the component classes like JButton, JTextField, JCheckbox, JMenu, etc.

The components of Swing are platform-independent, i.e., swing doesn't depend on the operating system to show the components. Also, the Swing's components are lightweight.


# Conclusion
By now I’m sure you understand exactly how our we can easily compress the file using simple using of function and send it anywhere at slow internet connections and vise versa and also learned about the java awt and java swing ,I hope y’all enjoyed reading this article as much as I enjoyed writing it!

## Authors

- [@areebkhan274427](https://github.com/areebkhan274427)


