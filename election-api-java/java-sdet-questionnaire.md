Questionnaires


***Q1***
Code Sample:
public class CultureMachineTestCases extends CultureMachineAssignment {

    CultureMachineTestCases testObj=new CultureMachineTestCases();

    @Before
    public void init() throws IOException{
        testObj.insertDataIntoSet();
        testObj.addKeywords("video1");

    }

    /*@Test
public void testVideo() throws IOException {
    result=testObj.search("abcd");
    answer=result.toString();
    answer1=answer.replaceAll("[^a-z0-9]","");

     assertEquals("video1", answer1);

}
@Before
public void initMethod() throws IOException{
    testObj.insertDataIntoSet();
    testObj.addKeywords("video2");
 }   */ @Test
  public void testLenth() throws IOException{
    flagVal=testObj.flag;

    assertEquals(1, flagVal);

    }
}


Error:
java.lang.StackOverflowError
    at cultureMachine.CultureMachineAssignment.<init>     (CultureMachineAssignment.java:13)
    at cultureMachine.CultureMachineTestCases.<init>(CultureMachineTestCases.java:11)
     at cultureMachine.CultureMachineTestCases.<init>(CultureMachineTestCases.java:14)
     at cultureMachine.CultureMachineTestCases.<init>(CultureMachineTestCases.java:14)
    at cultureMachine.CultureMachineTestCases.<init>(CultureMachineTestCases.java:14)
 java.lang.StackOverflowError
    at cultureMachine.CultureMachineAssignment.<init>     (CultureMachineAssignment.java:13)
    at cultureMachine.CultureMachineTestCases.<init>(CultureMachineTestCases.java:11)
    at cultureMachine.CultureMachineTestCases.<init>(CultureMachineTestCases.java:14)
    at cultureMachine.CultureMachineTestCases.<init>(CultureMachineTestCases.java:14)
    at cultureMachine.CultureMachineTestCases.<init>(CultureMachineTestCases.java:14)

    Main Java program:
    package cultureMachine;
        public class CultureMachineAssignment {

            HashMap<String,HashSet<String>> kewordVideo = new HashMap<String,HashSet<String>>();
            HashMap<String,HashSet<String>> videoKeyword =  new         HashMap<String,HashSet<String>>();
            HashMap<String,Integer> keywordLength = new HashMap<String,Integer>();

            HashSet<String> videoNames = new HashSet<String>();
            HashSet<String> result = new HashSet<String>();

            public void insertDataIntoSet(){
                for(int i=0;i<500;i++){
                    videoNames.add("video"+i);
                }
            }
            public void addKeywords(String video)throws IOException{


                InputStreamReader ip = new InputStreamReader(System.in);
                BufferedReader br = new BufferedReader(ip);

                Integer previousVal=0;

                if(!videoKeyword.containsKey(video) && videoNames.contains(video)){
                    videoKeyword.put(video,new HashSet<String>());
                }
                else if(!videoNames.contains(video)){
                    System.out.println("Video is not a part of lookup");
                }

                System.out.println("Enter keywords for video");
                String keyword =br.readLine();

                if(!keywordLength.containsKey(video))
                    keywordLength.put(video, 0);

                if((keywordLength.get(video)+keyword.length())<500){
                    videoKeyword.get(video).add(keyword);
                    previousVal=keywordLength.get(video);
                    keywordLength.put(video, previousVal+keyword.length());
                }
                else{
                    System.out.println("Maximum length exceeded for video "+ video);
                }
                if(!kewordVideo.containsKey(keyword)){
                    kewordVideo.put(keyword,new HashSet<String>());
                }
                kewordVideo.get(keyword).add(video);
            }

            public HashSet search(String searchKey){
                for (Entry<String, HashSet<String>> entry : videoKeyword.entrySet()) {
                    for (String s : entry.getValue()) {
                        if (s.contains(searchKey)) {
                            result.add(entry.getKey());
                        break;
                        }
                    }
                }
                return result;
            }

            public static void main(String args[]) throws IOException {

                CultureMachineAssignment obj1 = new CultureMachineAssignment();
                HashSet<String> searchResults = new HashSet<String>();
                int num=0;
                InputStreamReader ip = new InputStreamReader(System.in);
                BufferedReader br = new BufferedReader(ip);
                obj1.insertDataIntoSet();
                Scanner in = new Scanner(System.in);
                while(num!=3){
                    System.out.println();
                    System.out.println("Please enter your choice");
                    System.out.println("1. To assign keyword to video");
                    System.out.println("2. To Search Video using keyword");
                    System.out.println("3. Exit");

                    num=in.nextInt();

                    switch(num)
                    {
                    case 1 :
                        System.out.println("Enter Video name[video followed by video number]");
                        String video =br.readLine();
                        if(obj1.videoNames.contains(video))
                            obj1.addKeywords(video);
                        else
                            System.out.println(video+" is not a part of lookup");
                        break;
                    case 2 :
                        System.out.println("Enter partial or complete keyword to search video");
                        String searchKey = br.readLine();
                        searchResults=obj1.search(searchKey);
                        System.out.println(searchResults);
                        break;  
                    case 3:
                        System.out.println("exiting from application");
                        break;  
                    default:
                        System.out.println("Please enter correct choice");
                        break;  
                    }
                }
            }   
        }



***Q2***
Error while running JUnit tests:
java.lang.AssertionError: Expected exception: java.lang.IllegalArgumentException at org.junit.internal.runners.statements.ExpectException.evaluate(ExpectException.java:35) at org.junit.internal.runners.statements.RunBefores.evaluate(RunBefores.java:28) at org.junit.internal.runners.statements.RunAfters.evaluate(RunAfters.java:30) at org.junit.runners.ParentRunner.runLeaf(ParentRunner.java:263) at org.junit.runners.BlockJUnit4ClassRunner.runChild(BlockJUnit4ClassRunner.java:68) at org.junit.runners.BlockJUnit4ClassRunner.runChild(BlockJUnit4ClassRunner.java:47) at org.junit.runners.ParentRunner$3.run(ParentRunner.java:231) at org.junit.runners.ParentRunner$1.schedule(ParentRunner.java:60) at org.junit.runners.ParentRunner.runChildren(ParentRunner.java:229) at org.junit.runners.ParentRunner.access$000(ParentRunner.java:50) at org.junit.runners.ParentRunner$2.evaluate(ParentRunner.java:222) at org.junit.runners.ParentRunner.run(ParentRunner.java:300) at org.eclipse.jdt.internal.junit4.runner.JUnit4TestReference.run(JUnit4TestReference.java:50) at org.eclipse.jdt.internal.junit.runner.TestExecution.run(TestExecution.java:38) at org.eclipse.jdt.internal.junit.runner.RemoteTestRunner.runTests(RemoteTestRunner.java:467) at org.eclipse.jdt.internal.junit.runner.RemoteTestRunner.runTests(RemoteTestRunner.java:683) at org.eclipse.jdt.internal.junit.runner.RemoteTestRunner.run(RemoteTestRunner.java:390) at org.eclipse.jdt.internal.junit.runner.RemoteTestRunner.main(RemoteTestRunner.java:197)


***Q3***
I am using Junit 4. My whole program is working fine. I am trying to write a test case. But there is one error...

here is very basic sample test

public class di  extends TestCase{
    private static Records testRec;
    public void testAbc() {
        Assert.assertTrue(
            "There should be some thing.",
            di.testRec.getEmployee() > 0);
    }

}
and when i run this it give me error that

fName can not be null
if i use super and do like this

public TestA() {
super("testAbc");
}
it work all fine. It wasn't this before with JUnit 3.X am I doing wrong or they changed it :( Sorry if I am not clear

Is there any way to executre test without super? or calling functions etc. ?

***Q4***
i have an issue with Gatling. i want to do something simple.. lets say i have this Json in this variable and want to do a loadrunner style IDX. Somehow this is not possible??

get the count of where user == same
pick a random number from 0 to the above count
pick the corresponding book_title and put it in a variable
val testjson = """{
  "Books": [
    {
      "book_title": "bookTitle21",
      "user": "same"
    },
    {
      "book_title": "bookTitle73",
      "user": "same"
    },
    {
      "book_title": "bookTitle0",
      "user": "admin"
    }
  ]
}"""
so the outcome would be something like

val userCount = JonPath("$.Books.length").as[Int]

val randomIndex = util.Random.nextInt(userCount)

val randomBook = JsonPath("$.Books[#{randomIndex}].book_title", testjson) //this does not work

see the problem description;

tried alternatives like jmespath and jackson

***Q5***
I have a simple scenario, When I want to read the endpoints from the csv file in a circular. The request will be constructed based on the endpoint and same endpoint i need to pass to a function to generate a token and include in the headers.

val scn = scenario("Test").exitBlockOnFail{
    feed(csvFeeder)
    .group("Multiple tests") {
      exec(http("Multiple tests")
        .get("${endpoint}"+request_params)
        .headers(utils.HeaderUtils.create_header("${endpoint}").toMap)
        .check(status.is(200)))
    }.pause(1.seconds)
  }
The problem is, in the .get the ${endpoint} is replaced with actual value from the csv. But same value tried to pass to a fucntion under .headers the actual is not replaced. Its coming as string of ${endpoint} instead of the actual value from csv.

Can you please suggest here



        
