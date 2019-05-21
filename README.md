# convert-Any-String-Time-To-MiliSec
convert any string time (36:20 ,1:02:45 ,3213 s) to mili seconds

1-create Class Common.java


    public class Common {
    public static int convertAnyStringTimeToMilliSec(String stringTime) {
    int ItemTime = 0;
    int hour = 0;
    int minute = 0;
    int second = 0;

    String[] time = stringTime.split(":");
    switch (time.length) {
      case 1:
        try {

          second = parseInt(time[0]);
        }catch (Exception e){

        }
        ItemTime = second;
        break;
      case 2:
        try {
          minute = parseInt(time[0]);
          second = parseInt(time[1]);

        }catch (Exception e){

        }
        ItemTime = (minute * 60) + second;
        break;
      case 3:
        try {
          hour = parseInt(time[0]);
          minute = parseInt(time[1]);
          second = parseInt(time[2]);
        } catch (Exception e) {

        }
        ItemTime = (minute * 60) + (hour * 3600) + second;
        break;
    }
    return ItemTime * 1000;

     }
    }
    
 2-use this any where:
 
                int miliSec = convertAnyStringTimeToMilliSec(cureent.getTextContent());

