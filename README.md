# programming
## 가위바위보 게임 만들기 - 응용

    package scissors2;

    import java.util.Random;
    import java.util.Scanner;

    public class SW_20221065_2 {
	    public static void main (String args[]) {
    //		가위바위보를 통해 얻은 포인트에 따라 상품을 드립니다.
    //		5판: 1,000원 10판: 1,800원
    //		3포인트- 사탕꾸러미, 과자 5포인트- 키링, 인형, 미니쿠션 8포인트- 대형인형, 캘린더, 장난감
    //		상위 포인트를 얻은 사람은 하위 포인트 상품도 선택할 수 있습니다.
		
		    try {
            Thread.sleep(900);
            System.out.println("가위바위보를 통해 얻은 포인트에 따라 상품을 드립니다.");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
		
		    try {
            Thread.sleep(900);
            System.out.println("5판: 1,000원 10판: 1,800원");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
		
		    try {
            Thread.sleep(900);
            System.out.println("3포인트- 사탕꾸러미, 과자");
            System.out.println("5포인트- 키링, 인형, 미니쿠션");
            System.out.println("8포인트- 대형인형, 캘린더, 장난감");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
		
		    try {
            Thread.sleep(900);
            System.out.println("상위 포인트를 얻은 사람은 하위 포인트 상품도 선택할 수 있습니다.");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
		
		    try {
            Thread.sleep(900);
            System.out.println("당신이 가진 돈은?: ");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
		
		    Scanner scanner = new Scanner(System.in);
		    String value = scanner.nextLine();
		    int amount = Integer.parseInt(value.replaceAll("[^0-9]", ""));
		    int amount1 = 0;
		    int point = 0;
		    int tf = 0;
		
		    boolean stop = false;
		
		    while (!stop) {
		    try {
            Thread.sleep(900);
            System.out.println("몇 판 하실래요?: ");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
		
		    String number = scanner.nextLine();

		    if (number.equals("5판")) {
			      amount1 += 1000;
		    }else if (number.equals("10판")) {
			      amount1 += 1800;
		    }else {
            System.out.println("잘못된 입력입니다.");
            System.exit(0);
            stop = true;
            break;
            
        }
		
		    int whi = Integer.parseInt(number.replaceAll("[^0-9]", ""));
		    int result = amount - amount1;
		
		    if (result < 0) {
			    System.out.println("돈이 부족해요ㅠㅠ");
			    whi = 0;
		    }else {
			    System.out.println("남은 돈은"+result+"원입니다.");
			    System.out.println("게임을 시작합니다.");
		    }
		
		
		    for (int i = 0; i < whi; i++) {
			
			    System.out.println("무엇을 내시겠습니까? 1.가위 2.바위 3.보: ");
			    String answer = scanner.nextLine();
			    System.out.println("당신은 "+answer+"를 냈습니다.");
			
			    int data = 0;
			    Random random = new Random();
			    data = random.nextInt(3)+1;
			
			    String computer = "";
		    	if (data == 1) {
		    		computer = "가위";
		    	} else if (data == 2) {
		    		computer = "바위";
		    	} else {
			    	computer = "보";
			    }
			    System.out.println("컴퓨터는 "+computer);
			
			
			
		    	if ((data == 1 && answer.equals("가위"))||(data == 2 && answer.equals("바위"))||(data == 3 && answer.equals("보"))) {
	    			System.out.println("비겼어요!");
	    		} else if ((data == 1 && answer.equals("보"))||(data == 2 && answer.equals("가위"))||(data == 3 && answer.equals("바위"))) {
	    			System.out.println("컴퓨터가 이겼어요!");
		    	} else if ((data == 1 && answer.equals("바위"))||(data == 2 && answer.equals("보"))||(data == 3 && answer.equals("가위"))){
		    		System.out.println("당신이 이겼어요!");
			    	point += 1;
			    	System.out.println("포인트: "+point);
		    	} else {
			    	System.out.println("다시 입력하세요.");
				
			  }
		
	  	}
		
	  	try {
            Thread.sleep(950);
            System.out.println("누적 포인트는"+point);
            System.out.println("가위바위보 게임을 계속 하시겠습니까? : ");
      } catch (InterruptedException e) {
            e.printStackTrace();
      }
		
	  	String ctu = scanner.nextLine();			
		
	  	if (ctu.equals("아니요")) {
		  	if (point > 2) {
			  	System.out.println("상품을 수령하세요.");
			  	tf = 1;
			  	break;
		  	}else {
			  	System.out.println("시스템을 종료합니다.");
			  	System.exit(0);
			  	stop = true;
			   }
		  }else if (ctu.equals("네")){
		  	System.out.println("---------------------");
	  	}else {
		  	System.out.println("잘못된 입력입니다.");
		  	System.exit(0);
		  	stop = true;
	  	}

	  	}

		  if (tf == 1) {
			  if (5> point && point > 2) {
			  	System.out.println("[3포인트- 사탕, 과자] 중 한가지를 고르세요.:");
	  		}else if (8> point && point > 2) {
	  			System.out.println("[3포인트- 사탕, 과자], [5포인트- 키링, 인형, 미니쿠션] 중 한가지를 고르세요.:");
		  	}else if (point > 7) {
			  	System.out.println("[3포인트- 사탕, 과자], [5포인트- 키링, 인형, 미니쿠션], [8포인트- 대형인형, 캘린더, 장난감] 중 한가지를 고르세요.:");
  			}else {
	  			System.out.println("포인트가 모자라네요ㅜㅜ 다음 기회에 계속!");
		  		System.exit(0);;
			  }
  		}
	  	String present = scanner.nextLine();
		  System.out.println(present+"를 수령했습니다. 안녕히 가세요!");
  		scanner.close();
	  	System.exit(0);
	  }

    }
