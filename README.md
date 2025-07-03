#include <iostream>
#include<conio.h>
#include <random>
#include <string>
#include <ctime>

using namespace std;

int Q_NO = 1;
int CORRECT = 0;
int WRONG = 0;

//array declaration for maths
bool ask1[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask2[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask3[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };

//array declaration for science
bool ask4[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask5[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask6[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };

//array declaration for general knowledge
bool ask7[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask8[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask9[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };

//array declaration for english
bool ask10[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask11[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask12[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };

//array declaration for sports
bool ask13[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask14[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask15[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };

//array declaration for geography
bool ask16[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask17[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };
bool ask18[25] = { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };

//function prototype for maths easy
void display_random_question();
void displaymatheasy();
void question1(string question, string a, string b, string c, string d, char correct_answer);
void result();

//function prototype for maths medium
void display_random_question2();
void displaymathmed();
void question2(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for maths hard
void display_random_question3();
void displaymathhard();
void question3(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for science easy
void display_random_question4();
void displaysceasy();
void question4(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for science medium
void display_random_question5();
void displayscmed();
void question5(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for science hard
void display_random_question6();
void displayschard();
void question6(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for general knowledge easy
void display_random_question7();
void displaygkeasy();
void question7(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for general knowledge medium
void display_random_question8();
void displaygkmed();
void question8(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for general knowledge hard
void display_random_question9();
void displaygkhard();
void question9(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for english easy
void display_random_question10();
void displayengeasy();
void question10(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for general english medium
void display_random_question11();
void displayengmed();
void question11(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for general english hard
void display_random_question12();
void displayenghard();
void question12(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for sports easy
void display_random_question13();
void displayspeasy();
void question13(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for sports medium
void display_random_question14();
void displayspmed();
void question14(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for sports hard
void display_random_question15();
void displaysphard();
void question15(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for geography easy
void display_random_question16();
void displaygeoeasy();
void question16(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for geography medium
void display_random_question17();
void displaygeomed();
void question17(string question, string a, string b, string c, string d, char correct_answer);

//function prototype for geography hard
void display_random_question18();
void displaygeohard();
void question18(string question, string a, string b, string c, string d, char correct_answer);

//=================QUESTION BASED QUIZZES

//function prototype for Math easy
void QB_Maths_Easy();
void resultquiz(int correct, int wrong);

//function prototype for Math medium
void QB_Maths_Med();

// function prototype for Math hard
void QB_Maths_Hard();


//function prototype for Science easy
void QB_Science_Easy();

//function prototype for Science medium
void QB_Science_Med();

//function prototype for Science hard
void QB_Science_Hard();

//function prototype for generalknowledge easy
void QB_Gk_Easy();

//function prototype for generalknowledge medium
void QB_Gk_Med();

//function prototype for generalknowledge hard
void QB_Gk_Hard();

//function prototype for english easy
void QB_Eng_Easy();

//function prototype for english medium
void QB_Eng_Med();

//function prototype for english hard
void QB_Eng_Hard();

//function prototype for sports easy
void QB_Sports_Easy();

//function prototype for sports medium
void QB_Sports_Med();

//function prototype for sports hard
void QB_Sports_Hard();

//function prototype for geography easy
void QB_Geo_Easy();

//function prototype for geography medium
void QB_Geo_Med();

//function prototype for geography hard
void QB_Geo_Hard();


//=================TrueFalse Based Questions

//function prototype for Math easy
void MathsTrueFalseQuizzes();
void resulttrue(int correct, int wrong);

//function prototype for Math medium
void Maths_MediumTrueFalse();

// function prototype for Math hard
void Maths_HardTrueFalse();

//function prototype for Science easy
void Science_EasyTrueFalse();

//function prototype for Science medium
void Science_MediumTrueFalse();

//function prototype for Science hard
void Science_HardTrueFalse();

//function prototype for generalknowledge easy
void GeneralKnowledgeTrueFalse();

//function prototype for generalknowledge medium
void GeneralKnowledgeMediumTrueFalse();

//function prototype for generalknowledge hard
void GeneralKnowledgeHardTrueFalse();

//function prototype for english easy
void EnglishEasyTrueFalse();

//function prototype for english medium
void EnglishMediumTrueFalse();

//function prototype for english hard
void EnglishHardTrueFalse();

//function prototype for sports easy
void SportsEasyTrueFalse();

//function prototype for sports medium
void SportsMediumTrueFalse();

//function prototype for sports hard
void SportsHardTrueFalse();

//function prototype for geography easy
void GeographyEasyTrueFalse();

//function prototype for geography medium
void GeographyMediumTrueFalse();

//function prototype for geography hard
void GeographyHardTrueFalse();


int main()
{
    int choice;
    int mode;
    int topic;

    cout << "\tWelcome to Quiz Bot!" << endl << endl;

    int interface;
    cout << "1. Play ";
    cout << "\t\t2. Instructions" << endl;
    cout << "3. About";
    cout << "\t\t4. Tips" << endl << endl;
    cout << "Enter your choice: ";
    cin >> interface;


    system("cls");
    if (interface == 1)
    {

        cout << "\t\t";
        cout << "  ";
        cout << "Select the mode: \n\n";
        cout << "1. Single-player\n\n";
        cout << "Enter your choice: ";
        cin >> mode;

        system("cls");


        if (mode == 1) {

            cout << "\t\tMenu:" << endl << endl;
            cout << "1. MCQs";
            cout << "\t\t2. True/False" << endl;
            cout << "3. Quizzes" << endl << endl;
            cout << "Enter your choice: ";
            cin >> choice;


            system("cls");

            if (choice == 1) {
                cout << "Note: You selected MCQs." << endl << endl;
            }
            else if (choice == 2) {
                cout << "Note: You selected True/False." << endl << endl;
            }
            else if (choice == 3) {
                cout << "Note: You selected Quizzes." << endl << endl;
            }
            else {
                cout << "Invalid choice." << endl;
                return 0;
            }
        }



        cout << "\tSelect the topic:" << endl << endl;
        cout << "1. Mathematics";
        cout << "\t\t2. Science" << endl;
        cout << "3. General knowledge";
        cout << "\t4. English-Grammar" << endl;
        cout << "5. Sports";
        cout << "\t\t6. Geography" << endl;
        cout << "Enter your choice: ";
        cin >> topic;

        system("cls");

        switch (topic) {
        case 1:
            cout << "Note: You selected Mathematics." << endl << endl;
            break;
        case 2:
            cout << "Note: You selected Science." << endl << endl;
            break;
        case 3:
            cout << "Note: You selected General knowledge." << endl << endl;
            break;
        case 4:
            cout << "Note: You selected English-Grammar." << endl << endl;
            break;
        case 5:
            cout << "Note: You selected Sports." << endl << endl;
            break;
        case 6:
            cout << "Note: You selected Geography." << endl << endl;
            break;

        default:
            cout << "Invalid topic." << endl;
            return 0;
        }

        int difficulty;
        cout << "\tSelect the difficulty level:";
        cout << endl << endl;
        cout << "1. Easy";
        cout << "\t\t2. Medium" << endl;
        cout << "3. Hard" << endl << endl;
        cout << "Enter your choice: ";
        cin >> difficulty;

        system("cls");

        switch (difficulty) {
        case 1:
            cout << "Note: You selected easy difficulty." << endl << endl;
            break;
        case 2:
            cout << "You selected medium difficulty." << endl << endl;
            break;
        case 3:
            cout << "You selected hard difficulty." << endl << endl;
            break;
        default:
            cout << "Invalid difficulty level." << endl;
            return 0;
        }
        if (mode == 1 && choice == 1 && topic == 1 && difficulty == 1) //MATHS EASY MCQ
        {
            displaymatheasy();

        }
        else if (mode == 1 && choice == 1 && topic == 1 && difficulty == 2) //MATH MED MCQ
        {
            displaymathmed();
        }
        else if (mode == 1 && choice == 1 && topic == 1 && difficulty == 3) //MATH HARD MCQ
        {
            displaymathhard();
        }

        else if (mode == 1 && choice == 1 && topic == 2 && difficulty == 1) //Science EASY MCQ
        {
            displaysceasy();
        }
        else if (mode == 1 && choice == 1 && topic == 2 && difficulty == 2) //Science MED MCQ
        {
            displayscmed();
        }
        else if (mode == 1 && choice == 1 && topic == 2 && difficulty == 3) //Science HARD MCQ
        {
            displayschard();
        }

        else if (mode == 1 && choice == 1 && topic == 3 && difficulty == 1) //gk EASY MCQ
        {
            displaygkeasy();
        }
        else if (mode == 1 && choice == 1 && topic == 3 && difficulty == 2) //gk MED MCQ
        {
            displaygkmed();
        }
        else if (mode == 1 && choice == 1 && topic == 3 && difficulty == 3) //gk HARD MCQ
        {
            displaygkhard();
        }

        else if (mode == 1 && choice == 1 && topic == 4 && difficulty == 1) //ENG EASY MCQ
        {
            displayengeasy();
        }
        else if (mode == 1 && choice == 1 && topic == 4 && difficulty == 2) //ENG MED MCQ
        {
            displayengmed();
        }
        else if (mode == 1 && choice == 1 && topic == 4 && difficulty == 3) //ENG HARD MCQ
        {
            displayenghard();
        }

        else if (mode == 1 && choice == 1 && topic == 5 && difficulty == 1) //SPORTS EASY MCQ
        {
            displayspeasy();
        }
        else if (mode == 1 && choice == 1 && topic == 5 && difficulty == 2) //SPORTS MED MCQ
        {
            displayspmed();
        }
        else if (mode == 1 && choice == 1 && topic == 5 && difficulty == 3) //SPORTS HARD MCQ
        {
            displaysphard();
        }

        else if (mode == 1 && choice == 1 && topic == 6 && difficulty == 1) //GEO EASY MCQ
        {
            displaygeoeasy();
        }
        else if (mode == 1 && choice == 1 && topic == 6 && difficulty == 2) //GEO MED MCQ
        {
            displaygeomed();
        }
        else if (mode == 1 && choice == 1 && topic == 6 && difficulty == 3) //GEO HARD MCQ
        {
            displaygeohard();
        }
        //QUIZ

        else if (mode == 1 && choice == 3 && topic == 1 && difficulty == 1) //Math EASY QUIZ
        {
            QB_Maths_Easy();
        }
        else if (mode == 1 && choice == 3 && topic == 1 && difficulty == 2) //Math MED QUIZ
        {
            QB_Maths_Med();
        }
        else if (mode == 1 && choice == 3 && topic == 1 && difficulty == 3) //Math HARD Quiz   
        {
            QB_Maths_Hard();
        }


        else if (mode == 1 && choice == 3 && topic == 2 && difficulty == 1) //Science EASY QUIZ
        {
            QB_Science_Easy();
        }
        else if (mode == 1 && choice == 3 && topic == 2 && difficulty == 2) //Science MED QUIZ
        {
            QB_Science_Med();
        }
        else if (mode == 1 && choice == 3 && topic == 2 && difficulty == 3) //Science HARD Quiz    
        {
            QB_Science_Hard();
        }

        else if (mode == 1 && choice == 3 && topic == 3 && difficulty == 1) //gk EASY QUIZ
        {
            QB_Gk_Easy();
        }
        else if (mode == 1 && choice == 3 && topic == 3 && difficulty == 2) //gk MED QUIZ
        {
            QB_Gk_Med();
        }
        else if (mode == 1 && choice == 3 && topic == 3 && difficulty == 3) //gk HARD Quiz    
        {
            QB_Gk_Hard();
        }

        else if (mode == 1 && choice == 3 && topic == 4 && difficulty == 1) //english EASY QUIZ
        {
            QB_Eng_Easy();
        }
        else if (mode == 1 && choice == 3 && topic == 4 && difficulty == 2) //english MED QUIZ
        {
            QB_Eng_Med();
        }
        else if (mode == 1 && choice == 3 && topic == 4 && difficulty == 3) //english HARD Quiz    
        {
            QB_Eng_Hard();
        }

        else if (mode == 1 && choice == 3 && topic == 5 && difficulty == 1) //sports EASY QUIZ
        {
            QB_Sports_Easy();
        }
        else if (mode == 1 && choice == 3 && topic == 5 && difficulty == 2) //sports MED QUIZ
        {
            QB_Sports_Med();
        }
        else if (mode == 1 && choice == 3 && topic == 5 && difficulty == 3) //sports HARD Quiz    
        {
            QB_Sports_Hard();
        }

        else if (mode == 1 && choice == 3 && topic == 6 && difficulty == 1) //geography EASY QUIZ
        {
            QB_Geo_Easy();
        }
        else if (mode == 1 && choice == 3 && topic == 6 && difficulty == 2) //geography MED QUIZ
        {
            QB_Geo_Med();
        }
        else if (mode == 1 && choice == 3 && topic == 6 && difficulty == 3) //geography HARD Quiz    
        {
            QB_Geo_Hard();
        }

        //TRUE FALSE

        else if (mode == 1 && choice == 2 && topic == 1 && difficulty == 1) //Math EASY TRUEFALSE
        {
            MathsTrueFalseQuizzes();
        }
        else if (mode == 1 && choice == 2 && topic == 1 && difficulty == 2) //Math MED TRUEFALSE
        {
            Maths_MediumTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 1 && difficulty == 3) //Math HARD TRUEFALSE   
        {
            Maths_HardTrueFalse();
        }


        else if (mode == 1 && choice == 2 && topic == 2 && difficulty == 1) //Science EASY TRUEFALSE
        {
            Science_EasyTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 2 && difficulty == 2) //Science MED TRUEFALSE
        {
            Science_MediumTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 2 && difficulty == 3) //Science HARD TRUEFALSE   
        {
            Science_HardTrueFalse();
        }

        else if (mode == 1 && choice == 2 && topic == 3 && difficulty == 1) //gk EASY TRUEFALSE
        {
            GeneralKnowledgeTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 3 && difficulty == 2) //gk MED TRUEFALSE
        {
            GeneralKnowledgeMediumTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 3 && difficulty == 3) //gk HARD TRUEFALSE    
        {
            GeneralKnowledgeHardTrueFalse();
        }

        else if (mode == 1 && choice == 2 && topic == 4 && difficulty == 1) //english Easy TRUEFALSE
        {
            EnglishEasyTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 4 && difficulty == 2) //english Medium TRUEFALSE
        {
            EnglishMediumTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 4 && difficulty == 3) //english HARD TRUEFALSE    
        {
            EnglishHardTrueFalse();
        }

        else if (mode == 1 && choice == 2 && topic == 5 && difficulty == 1) //sports EASY TRUEFALSE
        {
            SportsEasyTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 5 && difficulty == 2) //sports MED TRUEFALSE
        {
            SportsMediumTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 5 && difficulty == 3) //sports HARD TRUEFALSE    
        {
            SportsHardTrueFalse();
        }

        else if (mode == 1 && choice == 2 && topic == 6 && difficulty == 1) //geography EASY TRUEFALSE
        {
            GeographyEasyTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 6 && difficulty == 2) //geography MED TRUEFALSE
        {
            GeographyMediumTrueFalse();
        }
        else if (mode == 1 && choice == 2 && topic == 6 && difficulty == 3) //geography HARD TRUEFALSE   
        {
            GeographyHardTrueFalse();
        }


    }
    if (interface == 2)
    {
        cout << "\t\tWelcome to Quiz Bot Instructions!" << endl << endl;
        cout << "Instructions:" << endl << endl;
        cout << "1. Select the desired Subject." << endl;
        cout << "2. Select the desired mode to play (MCQs, True False, Quizzes)\n";
        cout << "3. On selecting Multiple Choice Questions, User has to Follow the example given below" << endl << endl;
        cout << "4. MCQs:" << endl;
        cout << " User has to enter the correct option for example;\n\n" << "When was quiz bot created?\n" << "A. 2015\n" << "B. 2021\n" << "C. 2022\n" << "D. 2023\n" << "Enter the correct option: \"a\"\n\n";
        cout << "5. On selecting Question Bsed Quizzes, User has to Follow the example given below" << endl << endl;
        cout << "4. Quiz:" << endl;
        cout << " User has to enter the correct option for example;\n\n" << "When was quiz bot created?\n" << "Enter your answer: \" 2023\"\n\n";
        cout << "4. True False:" << endl;
        cout << " User has to enter the correct option for example;\n\n" << "Was Quiz Bot created in 2023?\n" << "Enter your answer(0 for False, 1 for True): \" 1\"\n\n";


    }

    if (interface == 3)
    {
        cout << "\t\tWelcome to Quiz Bot About Section!" << endl << endl;

        cout << "About:" << endl;
        cout << endl;
        cout << "1. Quiz Bot is a trivia game where you answer questions from various categories." << endl;
        cout << "2. The game will present you with multiple-choice questions, True False and Questions Based Quizzes" << endl;
        cout << "3. Each question will be marked and your winning criteria will be dependent upon more than 50% of correct answers" << endl;
        cout << "4. To start the game, simply follow the on-screen prompts and select your desired options." << endl;
        cout << "5. You can select the category of questions you want to play, such as Sports, Science, History, etc." << endl;
        cout << "6. You can also choose the difficulty level: Easy, Medium, or Hard." << endl;
        cout << "7. Once the game starts, read the question carefully and choose your answer by selecting the corresponding option." << endl;
        cout << "8. If your answer is correct, you will earn points." << endl;
        cout << "9. If your answer is incorrect, points will not be awarded, and you will move on to the next question." << endl;
        cout << "10. At the end of the game, you will receive a final score based on the number of correct answers." << endl;
        cout << "11. You can choose to play again or exit the game." << endl << endl;
        cout << "Quiz Bot is a trivia game developed by Zuhaib Abdullah, Jarrar Hussain, and Arib Razzaq." << endl;
        cout << "This game is presented to Sir Dawood and Sir Sauood as a project for Computer Programming course." << endl << endl;
    }

    if (interface == 4)
    {
        cout << "\t\tWelcome to Quiz Bot Tips Section!" << endl << endl;
        cout << "Tips:" << endl << endl;
        cout << "=> Pay attention to the category and difficulty level you select. Higher difficulty levels may have more challenging questions." << endl;
        cout << "=> Read each question carefully before selecting your answer. Sometimes, the correct answer may require careful consideration." << endl;
        cout << "=> Try to answer as quickly as possible to earn more points, but make sure to select the correct answer." << endl;
        cout << "=> Challenge yourself by playing in different categories and difficulty levels to expand your knowledge." << endl << endl;

        cout << "Enjoy playing Quiz Bot and have fun testing your trivia knowledge!" << endl;

    }


    _getch();
    return 0;

}

void displaymatheasy() //mcqs easy maths
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question();
}

void display_random_question()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask1[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask1[no])
        {
            ask1[no] = false;
            switch (no)
            {
            case 0:
                question1("How much is 24X2?", "28"
                    , "38", "48", "68", 'c');
                break;
            case 1:
                question1("0.75 is the same as?", "7.5%", "750", "75%", "0.075%", 'c');
                break;
            case 2:
                question1("The next prime number after 7 is?", "10", "11", "18", "14", 'b');
                break;
            case 3:
                question1("The perimeter of a circle is known as?", "Square", "Circumference ", "Pie", "Parallel", 'b');
                break;
            case 4:
                question1("How much is 65-43?", "33", "22", "32", "20", 'd');
                break;
            case 5:
                question1("Square root of 144 is?", "12", "11", "24", "13", 'a');
                break;
            case 6:
                question1("What comes after billion and trillion?", "Quadrillion", "Million", "Lakhs", "Multi-Trillion", 'd');
                break;
            case 7:
                question1("How many sides does a nonagon contain?", "10", "9", "8", "7", 'b');
                break;
            case 8:
                question1("Solve: 300 - (150 x 2)", "150", "100", "50", "0", 'd');
                break;
            case 9:
                question1("How much is 222+83?", "306", "305", "333", "304", 'd');
                break;
            case 10:
                question1("Total degrees in a right angle?", "90", "100", "80", "120", 'a');
                break;
            case 11:
                question1("What number should be added to 66 to get 121 as a sum?", "55", "66", "60", "44", 'a');
                break;
            case 12:
                question1("How much is 849 divided by 10?", "84.9", "8.49", "80", "85.94", 'a');
                break;
            case 13:
                question1("How many days and hours are equal to 200 hours?", "8 days and 8 hours", "9 days and 10 hours", "20 days and 20 hours", "10 days and 20 hours", 'a');
                break;
            case 14:
                question1("In 25,600, the place value of 6 is?", "600", "6", "6000", "60", 'd');
                break;
            case 15:
                question1("The least number of two digits is?", "99", "88", "11", "None of these", 'c');
                break;
            case 16:
                question1("A number can be divided by 5 if its unit digit is:", "0 or 5", "10 or 5", "2 or 6", "10 or 5", 'a');
                break;
            case 17:
                question1("The opposite of 6 is?", "-6", "9", "5", "7", 'a');
                break;
            case 18:
                question1("3/5th of 100 is?", "60", "20", "30", "65", 'a');
                break;
            case 19:
                question1("The remainder of 21 divided by 7 is?", "7", "21", "3", "None of these", 'c');
                break;
            case 20:
                question1("7% is equal to?", "0.007", "7", "0.7", "0.07", 'd');
                break;
            case 21:
                question1("How many years complete a decade?", "10", "5", "100", "50", 'a');
                break;
            case 22:
                question1("How many months are there in a century?", "1200", "120", "12000", "12", 'd');
                break;
            case 23:
                question1("How much is 90112 - 3123?", "96999", "76899", "86989", "86999", 'c');
                break;
            case 24:
                question1("What percentage should be added to 40 to make it 50?", "25", "90", "70", "15", 'a');
                break;
            }

        }

    }
    result();
}

void question1(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaymatheasy();
}

//mcqs maths medium

void displaymathmed()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question2();
}

void display_random_question2()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask2[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask2[no])
        {
            ask2[no] = false;
            switch (no) {
            case 0:
                question2("0.003 × 0.02 = ?", "0.06", "0.006", "0.0006", "0.00006", 'd');
                break;

            case 1:
                question2("What is the average of the numbers: 0, 0, 4, 10, 5, and 5?", "2", "3", "4", "5", 'c');
                break;

            case 2:
                question2("What is the rate of discount if a car which price was $4,000 was sold for $3,200?", "14%", "16%", "18%", "20%", 'd');
                break;

            case 3:
                question2("| –4 | +| 4 | – 4 + 4 = ?", "0", "2", "4", "8", 'a');
                break;

            case 4:
                question2("What is the value of x in the equation 3x – 15 – 6 = 0?", "7", "8", "9", "-9", 'a');
                break;

            case 5:
                question2("What is the area in cm2 of the shaded region in the diagram below?", "6", "7", "8", "9", 'a');
                break;

            case 6:
                question2("If A completes a particular work in 8 days and B completes the same work in 24 days. How many days will it take if they work together?", "4", "5", "6", "7", 'c');
                break;

            case 7:
                question2("What comes next in the sequence: 1, 3, 11, 43, ----?", "161", "171", "181", "191", 'b');
                break;

            case 8:
                question2("What is the distance traveled by a car which traveled at a speed of 80 km/hr for 3 hours and 30 minutes?", "275", "280", "285", "290", 'b');
                break;

            case 9:
                question2("In a class of 40 students, 20% are girls. How many boys are there in the class?", "26", "28", "30", "32", 'd');
                break;

            case 10:
                question2("2 + 2 − 2 × 2 ÷ 2 = ?", "0", "1", "2", "4", 'c');
                break;

            case 11:
                question2("What is the number called located on the bottom part of a fraction?", "numerator", "denominator", "componendo", "ratio", 'b');
                break;

            case 12:
                question2("If x = –1, then what is the value of the function?", "7", "9", "11", "13", 'a');
                break;

            case 13:
                question2("x = ?", "1", "-1", "2", "-2", 'b');
                break;

            case 14:
                question2("What comes next in the sequence: 2, 4, 10, 28, ----?", "64", "70", "76", "82", 'd');
                break;

            case 15:
                question2("What are the values of x and y in the following pair of equations?", "x = −2, y = −6", "x = 2, y = 6", "x = −3, y = −6", "x = 3, y = 6", 'd');
                break;

            case 16:
                question2("How many feet there are in 5 meters? If 1 meter = 3.281 feet?", "15.505", "15.905", "16.405", "16.805", 'c');
                break;

            case 17:
                question2("0.003 × 0.0004 = ?", "0.0012", "0.00012", "0.000012", "0.0000012", 'd');
                break;

            case 18:
                question2("What is the average (Arithmetic Mean) of the numbers: 2, 4, 5, 0, 9, 10, and 12?", "5", "6", "7", "8", 'b');
                break;

            case 19:
                question2("(2 ^ 2) ^ 3 ×(2 ^ 3) ^ 2 = ?", "4096", "4046", "3096", "3046", 'a');
                break;

            case 20:
                question2("What is the sum of 130 + 125 + 191?", "335", "446", "456", "476", 'b');
                break;

            case 21:
                question2("If we subtract 712 from 1500, how much do we get?", "788", "778", "776", "777", 'a');
                break;

            case 22:
                question2("50 times 8 is equal to:", "80", "400", "800", "4000", 'b');
                break;

            case 23:
                question2("110 divided by 10 is:", "11", "10", "5", "none of these", 'a');
                break;

            case 24:
                question2("20 + (90 ÷ 2) is equal to:", "50", "55", "65", "60", 'c');
                break;
            }

        }

    }
    result();
}

void question2(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaymathmed();
}


//MCQS MATHS HARD

void displaymathhard()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question3();
}

void display_random_question3()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask3[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask3[no])
        {
            switch (no) {
            case 0:
                question3("121 divided by 11 is:", "11", "10", "19", "18", 'a');
                break;

            case 1:
                question3("60 times 8 equals to:", "480", "300", "250", "400", 'a');
                break;

            case 2:
                question3("Find the missing term in multiples of 6: 6, 12, 18, 24, __, 36, 42, __, 54, 60.", "30, 48", "32, 45", "24, 40", "25, 49", 'a');
                break;

            case 3:
                question3("Add the decimals 5.23 + 8.79.", "14.02", "14.19", "14.11", "14.29", 'a');
                break;

            case 4:
                question3("Which among the following is the largest known number in the world?", "∞", "googol", "googolplex", "gram", 'c');
                break;

            case 5:
                question3("What does 1 googol mean?", "1 followed by hundred zeros", "1 followed by thousand zeros", "1 followed by ten thousand zeros", "1 followed by 1 lakh zeros", 'a');
                break;

            case 6:
                question3("Among the following, which whole number has no predecessor?", "–1", "0", "1", "e", 'b');
                break;

            case 7:
                question3("A number which is expressed as a + ib, where a and b are real, is called:", "Rational number", "Irrational number", "Complex number", "Real number", 'c');
                break;

            case 8:
                question3("An integer p, which is not 0 or ±1 and is divisible by no integer except ±1 and itself, is called:", "Rational number", "Perfect number", "Prime number", "Complex number", 'c');
                break;

            case 9:
                question3("p, p + 2, p + 4 are called _______ if all numbers are primes.", "Pythagorean Triplet", "Prime Triplet", "Lucas number", "Fermat number", 'b');
                break;

            case 10:
                question3("Which of the following is not a Pythagorean triplet?", "(3, 4, 5)", "(7, 24, 25)", "(11, 60, 61)", "(9, 41, 42)", 'd');
                break;

            case 11:
                question3("|2| + |–2| + (2)2 + (–2)2 = ?", "6", "8", "10", "12", 'c');
                break;

            case 12:
                question3("There are only 2 numbers that are twice the sum of their individual digits; one of them is zero (0). What is the other one?", "18", "27", "45", "40", 'a');
                break;

            case 13:
                question3("A system of notation that uses the base 3 instead of base 10 is called:", "Binary system", "Ternary system", "Hex system", "Octagonal system", 'b');
                break;

            case 14:
                question3("A system of notation that uses the base 2 instead of base 10 is called:", "Binary system", "Ternary system", "Hex system", "Hexagonal system", 'a');
                break;

            case 15:
                question3("Palindromic numbers are numbers that read the same backwards as forwards. The word \"Palindrome\" comes from the Greek word \"Palindromos.\" What is its meaning?", "Moving", "Kicking", "Running back again", "Laughing", 'c');
                break;

            case 16:
                question3("Which numbers appear in Dan Brown's best-selling novel \"The Da Vinci Code\"?", "Fermat number", "Fibonacci number", "Lucas number", "Golden number", 'b');
                break;

            case 17:
                question3("If P(n) is the statement \"n(n+1)(n+2) is divisible by 12,\" then what is P(3)?", "12 is divisible by 12", "24 is divisible by 12", "48 is divisible by 12", "60 is divisible by 12", 'd');
                break;

            case 18:
                question3("Which of these does not represent a unit of measurement?", "Line", "Rye seed", "Barleycorn", "Poppyseed", 'd');
                break;

            case 19:
                question3("What does 2 squared, plus the circumference of a circle, minus twice the product of the circle's radius and pi, minus the cube root of 8, equal?", "8", "4", "2", "6", 'c');
                break;

            case 20:
                question3("Who invented infinitesimal calculus independently of Newton, invented the binary system?", "Gottfried Leibniz", "Hermann Grassmann", "Johannes Kepler", "Heinrich Weber", 'a');
                break;

            case 21:
                question3("How many feet are there in a fathom?", "500", "100", "6", "12", 'c');
                break;

            case 22:
                question3("Which 3rd century Greek mathematician wrote Elements of Geometry?", "Archimedes", "Eratosthenes", "Euclid", "Pythagoras", 'c');
                break;

            case 23:
                question3("Four prime numbers are arranged in ascending order. The product of the first three is 385 and that of the last three is 1001. The largest prime number is:", "11", "13", "17", "9", 'b');
                break;

            case 24:
                question3("|2| + |–2| + (2)2 + (–2)2 = ?", "6", "8", "10", "12", 'c');
                break;
            }


        }

    }
    result();
}

void question3(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaymathhard();
}


//Science EASY MCQS

void displaysceasy() //mcqs easy science
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question4();
}

void display_random_question4()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask4[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask4[no])
        {
            ask4[no] = false;
            switch (no) {
            case 0:
                question4("Which of the following is a renewable source of energy?", "coal", "natural gas", "solar power", "nuclear power", 'c');
                break;

            case 1:
                question4("Which organ is responsible for pumping blood throughout the body?", "Lungs", "heart", "brain", "liver", 'b');
                break;

            case 2:
                question4("What is the chemical symbol for gold?", "Gd", "Ag", "Au", "Fe", 'c');
                break;

            case 3:
                question4("Which of the following is not a primary color of light?", "Red", "green", "yellow", "blue", 'b');
                break;

            case 4:
                question4("Total planets in our solar system", "6", "7", "8", "9", 'c');
                break;

            case 5:
                question4("Which is the largest planet of our solar system?", "Earth", "mars", "Saturn", "Jupiter", 'd');
                break;

            case 6:
                question4("Which is the smallest planet of our solar system?", "Mercury", "earth", "mars", "Uranus", 'a');
                break;

            case 7:
                question4("Sun is a ______", "planet", "star", "asteroid", "galaxy", 'b');
                break;

            case 8:
                question4("Which gas makes up the majority of Earth’s atmosphere?", "Nitrogen", "oxygen", "carbon dioxide", "hydrogen", 'a');
                break;

            case 9:
                question4("What is the basic unit of life?", "cells", "molecules", "organs", "tissues", 'a');
                break;

            case 10:
                question4("Water boils at", "0°C", "100°C", "50°C", "-100°C", 'b');
                break;

            case 11:
                question4("Water freezes at", "0°C", "100°C", "50°C", "-100°C", 'a');
                break;

            case 12:
                question4("Chemical formula of water is", "CO2", "NO2", "H2O", "NaCl", 'c');
                break;

            case 13:
                question4("Chemical formula of carbon", "CO2", "C", "CH", "H2O", 'b');
                break;

            case 14:
                question4("Which of the following is not a state of matter?", "Solid", "liquid", "gas", "energy", 'd');
                break;

            case 15:
                question4("What is the process by which plants convert sunlight into food?", "Respiration", "photosynthesis", "transpiration", "germination", 'b');
                break;

            case 16:
                question4("Which is the largest organ in the human body?", "Heart", "brain", "liver", "skin", 'd');
                break;

            case 17:
                question4("What is the process by which water changes from liquid to gas?", "Condensation", "evaporation", "sublimation", "precipitation", 'b');
                break;

            case 18:
                question4("What is the smallest unit of matter?", "Atom", "molecule", "cell", "particle", 'a');
                break;

            case 19:
                question4("Which of the following is responsible for carrying oxygen in the blood?", "Hemoglobin", "platelets", "white blood cells", "red blood cells", 'd');
                break;

            case 20:
                question4("What is the SI unit of force?", "Kilogram", "newton", "watt", "joule", 'b');
                break;

            case 21:
                question4("What Is the process by which a solid changes into a liquid?", "Evaporation", "sublimation", "melting", "freezing", 'c');
                break;

            case 22:
                question4("What is the pH value of a neutral substance?", "7", "0", "14", "1", 'a');
                break;

            case 23:
                question4("What is the outermost layer of Earth called?", "Crust", "mantle", "core", "lithosphere", 'a');
                break;

            case 24:
                question4("What is the primary function of white blood cells?", "Carrying oxygen", "blood clotting", "fighting infections", "transporting nutrients", 'c');
                break;
            }


        }

    }
    result();
}

void question4(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaysceasy();
}

//MCQS SCIENCE MED

void displayscmed()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question5();
}

void display_random_question5()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask5[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask5[no])
        {
            ask5[no] = false;
            switch (no) {
            case 0:
                question5("Which planet is known as the “red planet”?", "Earth", "Venus", "Mars", "Jupiter", 'c');
                break;

            case 1:
                question5("What Is the unit of measurement of electric current?", "Volt", "watt", "ampere", "ohm", 'c');
                break;

            case 2:
                question5("Which scientist is famous for his theory of relativity?", "Isaac Newton", "Albert Einstein", "Nikola Tesla", "Mac Miller", 'b');
                break;

            case 3:
                question5("What is the main component of Earth’s atmosphere?", "Nitrogen", "oxygen", "carbon dioxide", "water vapor", 'a');
                break;

            case 4:
                question5("What is the process by which plants release water vapors in the atmosphere?", "Transpiration", "photosynthesis", "respiration", "absorption", 'a');
                break;

            case 5:
                question5("What is the process by which a solid changes directly into a gas without becoming a liquid first?", "Condensation", "evaporation", "sublimation", "fusion", 'c');
                break;

            case 6:
                question5("Which of the following is not a form of energy?", "Thermal energy", "kinetic energy", "potential energy", "atomic energy", 'd');
                break;

            case 7:
                question5("What is the process by which an unstable atomic nucleus emits radiation?", "Fusion", "fission", "radioactivity", "sublimation", 'c');
                break;

            case 8:
                question5("Which of the following is not a component of the water cycle?", "Precipitation", "filtration", "condensation", "evaporation", 'b');
                break;

            case 9:
                question5("Which of the following is a greenhouse gas?", "Carbon", "oxygen", "nitrogen", "argon", 'c');
                break;

            case 10:
                question5("Which of the following is a renewable source of energy derived from organic matter?", "Geothermal energy", "nuclear energy", "tidal energy", "biomass energy", 'd');
                break;

            case 11:
                question5("Which of the following is not a type of rock?", "Granite", "basalt", "quartz", "limestone", 'c');
                break;

            case 12:
                question5("What Is the process by which an electric current passes through a gas, causing it to emit light?", "Incandescence", "fluorescence", "bioluminescence", "electroluminescence", 'b');
                break;

            case 13:
                question5("Which of the following is a vector quantity?", "Speed", "distance", "time", "velocity", 'd');
                break;

            case 14:
                question5("Which of the following is not a type of electromagnetic wave?", "X-ray", "ultraviolet", "sound wave", "gamma ray", 'c');
                break;

            case 15:
                question5("Which of the following is responsible for the sense of smell?", "Taste buds", "olfactory receptors", "retina", "eardrum", 'b');
                break;

            case 16:
                question5("What is the unit of measurement for electric resistance?", "Ampere", "ohm", "volt", "watt", 'b');
                break;

            case 17:
                question5("What is the primary function of white blood cells?", "Carrying oxygen", "blood clotting", "fighting infections", "transporting nutrients", 'c');
                break;

            case 18:
                question5("What is the largest organ in the human body by surface area?", "Brain", "skin", "lungs", "stomach", 'b');
                break;

            case 19:
                question5("What is the process by which heat is transferred through direct contact between particles of matter?", "Conduction", "convection", "radiation", "advection", 'a');
                break;

            case 20:
                question5("Which of the following is responsible for carrying genetic information in cells?", "Ribosomes", "mitochondria", "nucleus", "Golgi apparatus", 'c');
                break;

            case 21:
                question5("Which of the following is a renewable source of energy derived from the Earth’s internal heat?", "Solar energy", "wind energy", "geothermal energy", "biomass energy", 'd');
                break;

            case 22:
                question5("What is the smallest unit of an element that retains the chemical properties of that element?", "Cell", "atom", "molecule", "nucleus", 'b');
                break;

            case 23:
                question5("Which of the following is the largest organ in the human body by weight?", "Liver", "brain", "lungs", "kidney", 'a');
                break;

            case 24:
                question5("What is the SI unit of force?", "Kilogram", "newton", "watt", "joule", 'b');
                break;
            }


        }

    }
    result();
}

void question5(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displayscmed();
}


//  SCIENCE HARD MCQ

void displayschard()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question6();
}

void display_random_question6()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask6[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask6[no])
        {
            ask6[no] = false;
            switch (no) {
            case 0:
                question6("Which type of rock is formed from cooled lava or magma?", "Sedimentary rock", "Igneous rock", "metamorphic rock", "fossil rock", 'b');
                break;

            case 1:
                question6("What is the formula for calculating density?", "volume/mass", "volume x mass", "mass x volume", "mass/volume", 'd');
                break;

            case 2:
                question6("What Is the process by which plants convert nitrates into nitrogen gas?", "Nitrification", "denitrification", "nitrogen fixation", "nitrogen assimilation", 'b');
                break;

            case 3:
                question6("Which of the following is the largest organ in the human body by weight?", "Liver", "brain", "lungs", "kidney", 'a');
                break;

            case 4:
                question6("What is the study of Earth’s atmosphere and weather called?", "Geology", "meteorology", "astronomy", "biology", 'b');
                break;

            case 5:
                question6("What is the process by which an organism develops from a fertilized egg?", "Germination", "photosynthesis", "embryogenesis", "reproduction", 'c');
                break;

            case 6:
                question6("What Is the process by which an electric current pass through a gas, causing it to emit light?", "Incandescence", "fluorescence", "bioluminescence", "electroluminescence", 'b');
                break;

            case 7:
                question6("What is the study of interactions between organisms and their environment called?", "Ecology", "geology", "anthropology", "zoology", 'a');
                break;

            case 8:
                question6("Which of the following is not a phase of mitosis?", "Prophase", "metaphase", "interphase", "telophase", 'c');
                break;

            case 9:
                question6("Which of the following is an example of chemical change?", "Melting ice", "boiling water", "burning wood", "cutting paper", 'c');
                break;

            case 10:
                question6("What is the process by which heat is transferred through direct contact between particles of matter?", "Conduction", "convection", "radiation", "advection", 'a');
                break;

            case 11:
                question6("Which of the following is responsible for carrying genetic information in cells?", "Ribosomes", "mitochondria", "nucleus", "Golgi apparatus", 'c');
                break;

            case 12:
                question6("Which of the following is not a type of chemical bond?", "Covalent bond", "ionic bond", "hydrogen bond", "magnetic bond", 'd');
                break;

            case 13:
                question6("What is the study of Earth’s physical structure and substances called?", "Geology", "meteorology", "oceanology", "ecology", 'a');
                break;

            case 14:
                question6("Which of the following is not a fundamental force of nature?", "Gravity", "electromagnetic force", "nuclear force", "frictional force", 'd');
                break;

            case 15:
                question6("Which of the following is not a characteristic of acids?", "Sour taste", "turns litmus paper blue", "reacts with metal to produce hydrogen gas", "low pH value", 'b');
                break;

            case 16:
                question6("Which is the main site of photosynthesis in plant cells?", "Nucleus", "mitochondria", "chloroplasts", "endoplasmic reticulum", 'c');
                break;

            case 17:
                question6("What is the branch of biology that studies the classification and naming of organisms?", "Zoology", "botany", "taxonomy", "genetics", 'c');
                break;

            case 18:
                question6("Which of the following is the primary unit of energy in the metric system?", "Joule", "calorie", "newton", "watt", 'a');
                break;

            case 19:
                question6("What is the fourth state of matter?", "Nucleus", "cell", "gas", "plasma", 'd');
                break;

            case 20:
                question6("Which of the following is not a component of the circulatory system?", "Heart", "arteries", "lungs", "veins", 'c');
                break;

            case 21:
                question6("Which of the following is responsible for sense of hearing?", "Cochlea", "retina", "olfactory bulb", "taste buds", 'a');
                break;

            case 22:
                question6("Which of the following is not a form of energy?", "Mechanical energy", "chemical energy", "thermal energy", "static energy", 'd');
                break;

            case 23:
                question6("What is the unit to measure electric potential difference?", "Ampere", "volt", "ohm", "joule", 'b');
                break;

            case 24:
                question6("What is the SI unit of Pressure?", "Pascal", "newton", "joule", "volt", 'a');
                break;
            }


        }

    }
    result();
}

void question6(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displayschard();
}

//MCQS GK EASY

void displaygkeasy()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question7();
}

void display_random_question7()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask7[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask7[no])
        {
            ask7[no] = false;
            switch (no) {
            case 0:
                question7("Which country is called the land of cakes?", "Ireland", "Scotland", "Finland", "Netherlands", 'b');
                break;

            case 1:
                question7("2018 Olympics was played in _______?", "PyeongChang", "Tokyo", "Karachi", "Qatar", 'a');
                break;

            case 2:
                question7("What is the capital of Afghanistan?", "Zagreb", "Kandahar", "Jalalabad", "Kabul", 'd');
                break;

            case 3:
                question7("How many balls are used in play in the game of snooker?", "18", "20", "22", "24", 'c');
                break;

            case 4:
                question7("The Pakistan's Largest Tea Bag is made by which company?", "Tepal", "Lipton", "Tarang", "Brooke Bond", 'b');
                break;

            case 5:
                question7("What do you mean by the word 'Android'?", "Tough Animal", "Fast Eagle", "Human Like", "Tasty Food", 'c');
                break;

            case 6:
                question7("2023 cricket world cup will be hosted by _______?", "England", "India", "New Zealand", "Pakistan", 'b');
                break;

            case 7:
                question7("Which is the biggest desert in the world?", "Arctic Desert", "Sahara Desert", "Great Australian Desert", "Thar Desert", 'b');
                break;

            case 8:
                question7("The Islamic Consultative Assembly is the parliament of _______?", "Iraq", "Iran", "Afghanistan", "Albania", 'b');
                break;

            case 9:
                question7("What is the capital of the United States of America?", "New York", "Washington, D.C.", "California", "New Jersey", 'b');
                break;

            case 10:
                question7("The world's largest Muslim country by area is _______?", "Saudi Arabia", "Kazakhstan", "Pakistan", "Indonesia", 'b');
                break;

            case 11:
                question7("Eiffel Tower is located in which country?", "Network", "France", "Brussels", "India", 'b');
                break;

            case 12:
                question7("What does CPEC stand for?", "China Pakistan Electrical Coal", "China Pakistan Electronics Corporation", "China Pakistan Economic Corridor", "China Portugal Economical Corporation", 'c');
                break;

            case 13:
                question7("Which river does not flow from Jammu and Kashmir?", "Indus", "Jhelum", "Chenab", "Ravi", 'd');
                break;

            case 14:
                question7("Which country is the most popular destination for foreign tourists?", "Switzerland", "France", "Germany", "Australia", 'b');
                break;

            case 15:
                question7("What is the capital of Australia?", "Brisbane", "Brussels", "Beijing", "Doha", 'a');
                break;

            case 16:
                question7("Which color is produced by adding together yellow and cyan?", "Green", "Red", "Blue", "Pink", 'a');
                break;

            case 17:
                question7("What do you call a type of shape that has five sides?", "Triangle", "Circle", "Hexagon", "Pentagon", 'd');
                break;

            case 18:
                question7("How many equal sides does an isosceles triangle have?", "1", "2", "4", "8", 'b');
                break;

            case 19:
                question7("Which is the most widely spoken language in the world?", "English", "Hindi", "Spanish", "Mandarin", 'd');
                break;

            case 20:
                question7("Which is the largest 'Democracy' in the world?", "China", "USA", "India", "Denmark", 'c');
                break;

            case 21:
                question7("What color symbolizes peace?", "White", "Blue", "Green", "Black", 'a');
                break;

            case 22:
                question7("How many Cricket World Cups does India have?", "2", "3", "6", "1", 'a');
                break;

            case 23:
                question7("How many cards are there in a complete pack of cards?", "60", "62", "52", "56", 'c');
                break;

            case 24:
                question7("Which is the hardest substance available on Earth?", "Platinum", "Coal", "Diamond", "Gold", 'c');
                break;


            }


        }

    }
    result();
}

void question7(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaygkeasy();
}

//MCQS GK MED

void displaygkmed()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question8();
}

void display_random_question8()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask8[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask8[no])
        {
            ask8[no] = false;
            switch (no) {
            case 0:
                question8("Which is the World Highest Lake?", "Lake Titicaca", "Lake Victoria", "Lake Tana", "None", 'a');
                break;

            case 1:
                question8("Dead Sea located in which country?", "US", "Indonesia", "Jordan", "Belgium", 'c');
                break;

            case 2:
                question8("Indonesia is situated in?", "South-East Asia", "South Asia", "North-East Asia", "West Asia", 'a');
                break;

            case 3:
                question8("How many dots appear on a pair of dice?", "43", "45", "52", "42", 'd');
                break;

            case 4:
                question8("Which is the only body part that is fully grown from birth?", "Brain", "Eyes", "Ears", "Heart", 'b');
                break;

            case 5:
                question8("In what country was Elon Musk born?", "Romania", "Canada", "South Africa", "America", 'c');
                break;

            case 6:
                question8("How many hearts does an octopus have?", "2", "6", "1", "3", 'd');
                break;

            case 7:
                question8("What was the first soft drink consumed in space?", "Coca cola", "Sprite", "Pepsi", "Dr pepper", 'a');
                break;

            case 8:
                question8("What planet is closest to the sun?", "Mars", "Venus", "Mercury", "Earth", 'c');
                break;

            case 9:
                question8("Which country is known for consuming the highest amount of coffee per capita?", "Brazil", "United States", "Italy", "Finland", 'd');
                break;

            case 10:
                question8("What is the national sport of Japan?", "Judo", "Sumo Wrestling", "Karate", "Baseball", 'b');
                break;

            case 11:
                question8("Which country or territory has the highest life expectancy?", "Japan", "Switzerland", "Hong Kong", "Australia", 'c');
                break;

            case 12:
                question8("How many elements are currently recognized in the periodic table?", "92", "104", "118", "130", 'c');
                break;

            case 13:
                question8("How many bones are there in the human ear?", "1", "2", "3", "4", 'c');
                break;

            case 14:
                question8("Which bird is considered the fastest in the world?", "Bald Eagle", "Peregrine Falcon", "Golden Eagle", "Swift", 'b');
                break;

            case 15:
                question8("What is the currency of Denmark?", "Euro", "Pound", "Krona", "Krone", 'd');
                break;

            case 16:
                question8("What is the capital of New Zealand?", "Auckland", "Wellington", "Christchurch", "Sydney", 'b');
                break;

            case 17:
                question8("What is the smallest planet in our solar system?", "Mercury", "Venus", "Earth", "Mars", 'a');
                break;

            case 18:
                question8("How many human players are there on each side in a polo match?", "3", "4", "5", "6", 'b');
                break;

            case 19:
                question8("How many times has England won the men's football World Cup?", "0", "1", "2", "3", 'b');
                break;

            case 20:
                question8("How many years did the British Raj last in India?", "50 years", "75 years", "90 years", "110 years", 'c');
                break;

            case 21:
                question8("What does DC stand for in electrical terminology?", "Direct current", "Digital circuit", "Direct charge", "Dual conductor", 'a');
                break;

            case 22:
                question8("Which is the largest island in the world?", "Australia", "Greenland", "Madagascar", "Borneo", 'b');
                break;

            case 23:
                question8("What is a person who studies weather called?", "Biologist", "Meteorologist", "Geologist", "Astronomer", 'b');
                break;

            case 24:
                question8("Which gas is the most common in Earth's atmosphere?", "Oxygen", "Nitrogen", "Carbon dioxide", "Argon", 'b');
                break;
            }


        }

    }
    result();
}

void question8(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaygkmed();
}


//MCQS GK HARD

void displaygkhard()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question9();
}

void display_random_question9()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask9[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask9[no])
        {
            ask9[no] = false;
            switch (no) {
            case 0:
                question9("Which country was NOT part of the Soviet Union?", "Romania", "Ukraine", "Belarus", "Kazakhstan", 'a');
                break;

            case 1:
                question9("On what Japanese city was the first atomic bomb dropped?", "Tokyo", "Kyoto", "Hiroshima", "Nagasaki", 'c');
                break;

            case 2:
                question9("Which mammal is known to have the most powerful bite in the world?", "Lion", "Crocodile", "Elephant", "Hippopotamus", 'd');
                break;

            case 3:
                question9("How many balls are on a pool table at the start of a game?", "8", "10", "12", "16", 'd');
                break;

            case 4:
                question9("Generally, which component of a computer draws the most power?", "Central Processing Unit (CPU)", "Random Access Memory (RAM)", "Hard Disk Drive (HDD)", "Video Card (GPU)", 'd');
                break;

            case 5:
                question9("What color is the 8 ball in a game of pool?", "Red", "Blue", "Yellow", "Black", 'd');
                break;

            case 6:
                question9("When was the iPhone released?", "2004", "2006", "2007", "2009", 'c');
                break;

            case 7:
                question9("Which country won the first Football World Cup?", "Brazil", "Argentina", "Uruguay", "Germany", 'c');
                break;

            case 8:
                question9("When Gmail first launched, how much storage did it provide for your email?", "500MB", "1GB", "2GB", "5GB", 'b');
                break;

            case 9:
                question9("How many players are in a basketball team?", "Three", "Four", "Five", "Six", 'c');
                break;

            case 10:
                question9("How many players make up a field hockey team?", "Eight", "Nine", "Ten", "Eleven", 'd');
                break;

            case 11:
                question9("A baby goat is called what?", "Calf", "Foal", "Kid", "Lamb", 'c');
                break;

            case 12:
                question9("What's a group of kittens called?", "Litter", "Pack", "Flock", "Kindle", 'd');
                break;

            case 13:
                question9("In which country did table tennis originate?", "China", "The UK", "France", "Germany", 'b');
                break;

            case 14:
                question9("How many points do we need to win a single game in table tennis?", "7 points", "11 points", "15 points", "10 points", 'b');
                break;

            case 15:
                question9("What can be broken but is never held?", "Glass", "A promise", "A rock", "A mirror", 'b');
                break;

            case 16:
                question9("What comes down but never goes up?", "Snow", "Birds", "Rain", "Airplanes", 'c');
                break;

            case 17:
                question9("MS-Word is an example of _____", "An Operating system", "A processing device", "Application software", "An input device", 'c');
                break;

            case 18:
                question9("Ctrl, Shift and Alt are called .......... keys.", "Modifier", "Function", "Alphanumeric", "Adjustment", 'a');
                break;

            case 19:
                question9("The atmosphere of the Earth is mainly Nitrogen and", "Oxygen", "Carbon dioxide", "Hydrogen", "Argon", 'a');
                break;

            case 20:
                question9("Recep Tayyip Erdogan has been president of Turkey since", "2010", "2012", "2014", "2016", 'c');
                break;

            case 21:
                question9("Who is currently the king of United Kingdom (UK)?", "Charles II", "Charles III", "Andrew", "Andrew II", 'b');
                break;

            case 22:
                question9("The current US president Joe Biden has also served as ________ of the United States.", "director CIA", "speaker", "secretary state", "vice president", 'd');
                break;

            case 23:
                question9("What play the most important role in regulating temperature and determining climate on the Earth?", "Oceans", "Mountains", "Deserts", "Forests", 'a');
                break;

            case 24:
                question9("How many galaxies are there in the universe?", "10 million", "100 million", "10 billion", "100 billion", 'd');
                break;


            }


        }

    }
    result();
}

void question9(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaygkhard();
}

//ENGLISH EASY MCQS

void displayengeasy()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question10();
}

void display_random_question10()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask10[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask10[no])
        {
            ask10[no] = false;
            switch (no) {
            case 0:
                question10("Which of the following is a pronoun?", "Dog", "running", "she", "green", 'c');
                break;

            case 1:
                question10("What is the past tense of the verb 'eat'?", "Eaten", "Ate", "Eating", "Eat", 'b');
                break;

            case 2:
                question10("What is the opposite of the word 'cold'?", "Hot", "warm", "freezing", "cool", 'a');
                break;

            case 3:
                question10("What is the synonym for 'happy'?", "Sad", "angry", "joyful", "tired", 'c');
                break;

            case 4:
                question10("Every sentence must have a subject and ____", "a verb", "an object", "an adverb", "a conjunction", 'a');
                break;

            case 5:
                question10("Adjectives usually come", "before a noun", "after a noun", "after a pronoun", "before a verb", 'a');
                break;

            case 6:
                question10("Which is correct?", "Your looking good", "your look good", "you're look good", "you're looking good", 'd');
                break;

            case 7:
                question10("What would you do if it _____ on your wedding day?", "Will rain", "would rain", "rained", "shall rain", 'c');
                break;

            case 8:
                question10("If they had not _____ the car, I would have driven you", "take", "taken", "would take", "will take", 'b');
                break;

            case 9:
                question10("If she comes, I _____ call you.", "Will", "would", "would have", "would have been", 'a');
                break;

            case 10:
                question10("If it snows, ____ still drive to the coast?", "Would you", "would you have", "shall you", "will you", 'd');
                break;

            case 11:
                question10("My grandparents walk _____ twenty minutes a day.", "For", "since", "with", "none", 'a');
                break;

            case 12:
                question10("The lady has been waiting for the bus ______ noon", "For", "since", "with", "none", 'b');
                break;

            case 13:
                question10("I dislike _____ to the movies by myself", "To go", "to went", "going", "go", 'c');
                break;

            case 14:
                question10("Our neighbor used ______ a pipe", "smoking", "to smoking", "smoke", "to smoke", 'd');
                break;

            case 15:
                question10("Identify the verb in the following sentence: 'The dog chased the ball.'", "Dog", "chased", "ball", "none", 'b');
                break;

            case 16:
                question10("Choose the correct possessive form of the noun: 'cat'.", "Cats's", "cat'ss", "cats'", "cat's", 'd');
                break;

            case 17:
                question10("I ______ to the store yesterday.", "Goes", "gone", "go", "went", 'd');
                break;

            case 18:
                question10("What is the past tense of the verb 'run'?", "Runned", "ran", "run", "none", 'b');
                break;

            case 19:
                question10("Choose the correct spelling", "exercsise", "excersice", "exercise", "excersise", 'c');
                break;

            case 20:
                question10("Which word is the conjunction in the sentence 'I like both ice cream and cake.'", "Like", "both", "and", "none", 'c');
                break;

            case 21:
                question10("Which word is the adverb in the sentence 'She sings beautifully'", "She", "sings", "beautifully", "none", 'c');
                break;

            case 22:
                question10("Choose the correct spelling", "pursue", "purseu", "persue", "persuee", 'a');
                break;

            case 23:
                question10("Choose the correct spelling", "receive", "recieve", "receeve", "receievee", 'a');
                break;

            case 24:
                question10("Which of the following is a preposition?", "Run", "jump", "on", "sleep", 'c');
                break;
            }


        }

    }
    result();
}

void question10(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displayengeasy();
}

//MCQS ENGLISH MEDIUM

void displayengmed()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question11();
}

void display_random_question11()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask11[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask11[no])
        {
            ask11[no] = false;
            switch (no) {
            case 0:
                question11("He would have gone with you if you asked him. Which conditional is this?", "First", "second", "third", "none", 'c');
                break;

            case 1:
                question11("If I won a million dollars, I would buy an airplane. Which conditional is this?", "Zero", "first", "second", "third", 'c');
                break;

            case 2:
                question11("We started _____ dinner without you.", "Eating", "to eat", "eating/to eat", "none", 'c');
                break;

            case 3:
                question11("My teacher said my essay needs _____ by tomorrow.", "To correct", "correcting", "corrected", "correct", 'b');
                break;

            case 4:
                question11("She ________ lunch by the time we arrived.", "Had finished", "finished", "have finished", "finishing", 'a');
                break;

            case 5:
                question11("____ you ever _____ to Hollywood?", "Did...go", "have...go", "have...gone", "shall...go", 'c');
                break;

            case 6:
                question11("Yes, that is the woman _________ horse almost trampled her!", "Which", "whose", "who", "that", 'b');
                break;

            case 7:
                question11("I have ____ been to Paris.", "Never", "ever", "always", "often", 'a');
                break;

            case 8:
                question11("Identify the correct comparative form of the adjective 'good'", "gooder", "better", "more good", "goodest", 'b');
                break;

            case 9:
                question11("Synonym of 'diligent'", "Lazy", "hardworking", "careless", "stupid", 'b');
                break;

            case 10:
                question11("Synonym of 'vibrant'", "Dull", "stay", "gloomy", "lively", 'd');
                break;

            case 11:
                question11("Synonym of 'furious'", "calm", "content", "enraged", "slow", 'c');
                break;

            case 12:
                question11("Choose the correct spelling", "indecisive", "indesisive", "endecisive", "indisicive", 'a');
                break;

            case 13:
                question11("Antonym of 'brave'", "courageous", "heroic", "peaceful", "fearful", 'd');
                break;

            case 14:
                question11("Antonym of 'expand'", "contract", "enlarge", "extend", "serene", 'a');
                break;

            case 15:
                question11("Choose the correct possessive form of the noun 'child'", "childs'", "child's", "childs", "childs's", 'b');
                break;

            case 16:
                question11("What is the comparative form of the adverb 'quickly'?", "Quicklier", "quick", "quickliest", "more quickly", 'd');
                break;

            case 17:
                question11("Identify the preposition in the following sentence: 'the book is on the table.'", "the", "book", "is", "on", 'd');
                break;

            case 18:
                question11("What is the comparative form of the adjective 'bad'", "badly", "badder", "worse", "badderly", 'c');
                break;

            case 19:
                question11("What is the plural of the word 'mouse'", "mouses", "mouse", "mice", "mices", 'c');
                break;

            case 20:
                question11("What is the plural of the word 'sheep'", "sheeps", "sheep", "sheps", "sheeps's", 'b');
                break;

            case 21:
                question11("Identify the indirect object in the following sentence: 'She gave her friend a gift'", "She", "gave", "her friend", "gift", 'c');
                break;

            case 22:
                question11("Synonym of 'excited'", "thrilled", "bored", "tired", "worried", 'a');
                break;

            case 23:
                question11("Choose the correct spelling", "excatic", "ecstatic", "estatic", "esctatic", 'b');
                break;

            case 24:
                question11("Synonym of 'persistent'", "determined", "flexible", "indecisive", "plentiful", 'a');
                break;
            }


        }

    }
    result();
}

void question11(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displayengmed();
}
//MCQS English Hard

void displayenghard()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question12();
}

void display_random_question12()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask12[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask12[no])
        {
            ask12[no] = false;
            switch (no) {
            case 0:
                question12("If I forget her birthday, Andrea gets upset. Which conditional is this?", "Zero", "first", "second", "third", 'a');
                break;

            case 1:
                question12("Choose the correct spelling", "brocolli", "broccoli", "broccolli", "brocoly", 'b');
                break;

            case 2:
                question12("Choose the correct spelling", "manouver", "manuever", "manuver", "maneuver", 'd');
                break;

            case 3:
                question12("I’m afraid I’m not hungry. I’ve _____ eaten lunch.", "yet", "still", "already", "ever", 'c');
                break;

            case 4:
                question12("Fiestas ______________ in Cologne, Germany for many years now.", "Have been making", "have made", "have been made", "are made", 'c');
                break;

            case 5:
                question12("Synonym of 'persistent'", "determined", "flexible", "indecisive", "plentiful", 'a');
                break;

            case 6:
                question12("Antonym of 'subtle'", "discreet", "delicate", "obvious", "lazy", 'c');
                break;

            case 7:
                question12("What is the plural of the word 'moose'", "moose", "mooses", "mooses's", "moosess", 'a');
                break;

            case 8:
                question12("Which of the following word is spelled correctly", "exhilirate", "rhythm", "millenium", "embarrasment", 'b');
                break;

            case 9:
                question12("The teacher asked the students to ______ quietly", "settle", "sits", "sat", "sit", 'd');
                break;

            case 10:
                question12("Identify the figure of speech used in the following sentence: 'his words were a soothing balm for her troubled soul.'", "Metaphor", "simile", "personification", "hyperbole", 'a');
                break;

            case 11:
                question12("She _____ the prize in the singing competition.", "one", "when", "won", "weighed", 'c');
                break;

            case 12:
                question12("Synonym of 'ephemeral'", "permanent", "enduring", "transient", "lasting", 'c');
                break;

            case 13:
                question12("Choose the word that is closest in meaning to 'ubiquitous'", "rare", "common", "scarce", "exceptional", 'b');
                break;

            case 14:
                question12("Identify the type of sentence 'She won the race, didn’t she?'", "Declarative", "imperative", "interrogative", "exclamatory", 'c');
                break;

            case 15:
                question12("What is the correct synonym of the word 'pulchritudinous'", "ugly", "attractive", "mundane", "repulsive", 'b');
                break;

            case 16:
                question12("As whisper is to speak, tiptoe is to _____", "run", "dance", "shout", "walk", 'd');
                break;

            case 17:
                question12("Identify the sentence that contains a double negative", "I can’t find my keys anywhere", "I don’t want no dessert", "she doesn’t have any money", "he never eats vegetables", 'b');
                break;

            case 18:
                question12("The cat is sleeping _____ the couch", "under", "above", "below", "over", 'a');
                break;

            case 19:
                question12("As pen is to write, brush is to ______", "paint", "draw", "scrabble", "erase", 'a');
                break;

            case 20:
                question12("As tree is to leaves, flower is to _____", "stem", "thorns", "roots", "petals", 'd');
                break;

            case 21:
                question12("As book is to read, movie is to ________", "act", "direct", "watch", "listen", 'c');
                break;

            case 22:
                question12("Synonym of 'pensive'", "joyful", "thoughtful", "cheerful", "carefree", 'b');
                break;

            case 23:
                question12("As victory is to triumph, defeat is to _____", "sorrow", "celebrate", "loss", "challenge", 'c');
                break;

            case 24:
                question12("As venomous is to poison, infectious is to _______", "disease", "cure", "medicine", "virus", 'd');
                break;
            }


        }

    }
    result();
}

void question12(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displayenghard();
}


//MCQS Sports Easy

void displayspeasy()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question13();
}

void display_random_question13()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask13[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask13[no])
        {
            ask13[no] = false;
            switch (no) {
            case 0:
                question13("Who is the first Pakistani to hit a century in T20I cricket?", "Imran Nazir", "Kamran Akmal", "Ahmad Shahzad", "Shahid Afridi", 'c');
                break;

            case 1:
                question13("In which year did Pakistan play its first test match?", "1951", "1952", "1953", "1954", 'b');
                break;

            case 2:
                question13("How many points are there in badminton?", "11", "21", "31", "41", 'b');
                break;

            case 3:
                question13("ICC stands for ______________.", "International cricket conference", "International cricket council", "International cricket club", "International cricket coalition", 'b');
                break;

            case 4:
                question13("Who has scored the most goals ever in football history?", "Ronaldo", "Maradona", "Pele", "Zidane", 'c');
                break;

            case 5:
                question13("Pakistan lost the cricket World Cup final in ____________?", "1992", "1996", "1999", "2003", 'c');
                break;

            case 6:
                question13("Durand Cup is associated with the game of:", "Football", "Squash", "Volleyball", "Table Tennis", 'a');
                break;

            case 7:
                question13("Which Country's Balls were used for the 2018 FIFA World Cup?", "Pakistan", "India", "Sri Lanka", "Thailand", 'a');
                break;

            case 8:
                question13("How many players are there on a football team?", "10 players", "12 players", "11 players", "13 players", 'c');
                break;

            case 9:
                question13("Which team got the 3rd position in the FIFA World Cup 2018?", "France", "England", "Croatia", "Belgium", 'c');
                break;

            case 10:
                question13("Which sport is known as 'the beautiful game'?", "Basketball", "Rugby", "Cricket", "Soccer", 'd');
                break;

            case 11:
                question13("In which sport is a 'hole-in-one' a highly coveted achievement?", "Golf", "Tennis", "Swimming", "Cycling", 'a');
                break;

            case 12:
                question13("Which country is known for its dominance in swimming?", "United States", "Australia", "China", "Russia", 'd');
                break;

            case 13:
                question13("In which sport is the term 'ace' used?", "Golf", "Soccer", "Tennis", "Baseball", 'c');
                break;

            case 14:
                question13("Which sport is played on a diamond-shaped field?", "Soccer", "Baseball", "Basketball", "Volleyball", 'b');
                break;

            case 15:
                question13("How many players are there on a volleyball team?", "4 players", "6 players", "8 players", "10 players", 'b');
                break;

            case 16:
                question13("Which country is known for its strong presence in rugby?", "New Zealand", "England", "South Africa", "All of the above", 'd');
                break;

            case 17:
                question13("In which sport are 'aces' and 'love' commonly used terms?", "Tennis", "Golf", "Basketball", "Swimming", 'a');
                break;

            case 18:
                question13("Which country has won the most FIFA World Cup titles?", "Brazil", "Germany", "Italy", "Argentina", 'a');
                break;

            case 19:
                question13("In which sport is the Stanley Cup awarded to the champion team?", "Ice hockey", "Tennis", "Volleyball", "Golf", 'a');
                break;

            case 20:
                question13("In which sport is a 'home run' a highly valued achievement?", "Basketball", "Baseball", "Soccer", "Swimming", 'b');
                break;

            case 21:
                question13("How many players are there on a hockey team?", "5 players", "7 players", "11 players", "6 players", 'd');
                break;

            case 22:
                question13("Which country is known for its strong presence in basketball?", "United States", "Spain", "Argentina", "Canada", 'a');
                break;

            case 23:
                question13("In which sport are 'birdies' and 'eagles' commonly used terms?", "Tennis", "Golf", "Soccer", "Baseball", 'b');
                break;

            case 24:
                question13("Which country is known for its dominance in Formula 1 racing?", "Germany", "United Kingdom", "Italy", "All of the above", 'd');
                break;
            }


        }

    }
    result();
}

void question13(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displayspeasy();
}


//MCQS Sports Medium

void displayspmed()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question14();
}

void display_random_question14()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask14[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask14[no])
        {
            ask14[no] = false;
            switch (no) {
            case 0:
                question14("'Bull's eye' is used in the game of", "Shooting", "Boxing", "Polo", "Baseball", 'a');
                break;

            case 1:
                question14("Which of the following trophies is not awarded in cricket?", "Ashes", "Ryder Cup", "Champions Trophy", "Asia Cup", 'b');
                break;

            case 2:
                question14("For the first time, the Commonwealth Games were played during 1930 in", "Canada", "London", "Brazil", "Pakistan", 'a');
                break;

            case 3:
                question14("With which sport do you associate the name of Rod Laver?", "Football", "Water Polo", "Field Hockey", "Lawn Tennis", 'd');
                break;

            case 4:
                question14("What is the width of the goal post in the game of football?", "20 feet", "22 feet", "24 feet", "26 feet", 'c');
                break;

            case 5:
                question14("Jahangir Khan is famous in which sport?", "Squash", "Boxing", "Cricket", "Hockey", 'a');
                break;

            case 6:
                question14("Which of the following terms is not associated with football?", "Free Kick", "Offside", "Penalty Kick", "Penalty Stroke", 'd');
                break;

            case 7:
                question14("Which cricketer holds the record for scoring the highest number of runs in a test match innings?", "Brian Lara", "Sunil Gavaskar", "Gary Sobers", "Vivian Richards", 'a');
                break;

            case 8:
                question14("When was the first Commonwealth Games held?", "1930", "1934", "1938", "1948", 'a');
                break;

            case 9:
                question14("In which sport is the participant called a pugilist?", "Sprinter", "Boxing", "Wrestling", "Javelin throw", 'b');
                break;

            case 10:
                question14("The term 'Butterfly Stroke' is referred to in which sport?", "Wrestling", "Volleyball", "Tennis", "Swimming", 'd');
                break;

            case 11:
                question14("In which game is the term 'Putting' used?", "Chess", "Hockey", "Golf", "Billiards", 'c');
                break;

            case 12:
                question14("The term 'Beamer' is associated with which sport?", "Cricket", "Hockey", "Chess", "Football", 'a');
                break;

            case 13:
                question14("The Thomas Cup is related to which sport?", "Tennis", "Cricket", "Basketball", "Badminton", 'd');
                break;

            case 14:
                question14("The Ryder Cup is related to which sport?", "Cricket", "Badminton", "Golf", "Football", 'c');
                break;

            case 15:
                question14("The number of players on each side in Water Polo is:", "6", "7", "8", "9", 'b');
                break;

            case 16:
                question14("Which was the first country to host the Asian Games?", "China", "Japan", "India", "Korea", 'c');
                break;

            case 17:
                question14("Where is the headquarters of the International Olympic Committee located?", "Italy", "France", "Belgium", "Switzerland", 'd');
                break;

            case 18:
                question14("Serena Williams is one of the top-ranked sportswomen of", "Chess", "Tennis", "Shooting", "Badminton", 'b');
                break;

            case 19:
                question14("The distance of a marathon race is", "24 miles 385 yards", "26 miles 385 yards", "25 miles 385 yards", "28 miles 385 yards", 'b');
                break;

            case 20:
                question14("What is the maximum permitted length of a cricket bat?", "36\"", "37\"", "38\"", "39\"", 'c');
                break;

            case 21:
                question14("Which of the following Twenty-20 Cricket Rules is not correctly stated?", "A bowler can bowl a maximum of 6 overs per innings", "Fielding restrictions are applicable for the first six overs of the innings", "Each inning has a time limit of 75 minutes. For every over bowled after that, the batting side gets extra 6 runs", "If a batsman fails to reach the crease within 90 seconds after the fall of a wicket, the bowling side gets 5 penalty runs", 'a');
                break;

            case 22:
                question14("After how many years is the FIFA World Cup held?", "2 Years", "3 Years", "4 Years", "Every Year", 'c');
                break;

            case 23:
                question14("Which country won the first FIFA World Cup?", "Argentina", "Uruguay", "Italy", "Brazil", 'b');
                break;

            case 24:
                question14("Who won the first T20 World Cup?", "Pakistan", "India", "Sri Lanka", "West Indies", 'b');
                break;
            }


        }

    }
    result();
}

void question14(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displayspmed();
}

//MCQS Sports Hard

void displaysphard()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question15();
}

void display_random_question15()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask15[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask15[no])
        {
            ask15[no] = false;
            switch (no) {
            case 0:
                question15("Who holds the record for the most home runs in Major League Baseball (MLB) history?", "Babe Ruth", "Barry Bonds", "Hank Aaron", "Alex Rodriguez", 'b');
                break;

            case 1:
                question15("In Olympic weightlifting, what is the term for the lift where the barbell is brought from the ground to the shoulders in one fluid motion?", "Clean and jerk", "Snatch", "Clean and press", "Power clean", 'b');
                break;

            case 2:
                question15("Which country has won the most FIFA World Cup titles?", "Brazil", "Germany", "Italy", "Argentina", 'a');
                break;

            case 3:
                question15("Who holds the record for the most goals scored in a single season of the English Premier League?", "Alan Shearer", "Cristiano Ronaldo", "Thierry Henry", "Harry Kane", 'a');
                break;

            case 4:
                question15("In which sport is the term 'reverse swing' commonly used?", "Cricket", "Golf", "Tennis", "Basketball", 'a');
                break;

            case 5:
                question15("Who is the only athlete to have won Olympic gold medals in both the 100 meters and 200 meters races for three consecutive Olympics?", "Carl Lewis", "Usain Bolt", "Jesse Owens", "Michael Johnson", 'b');
                break;

            case 6:
                question15("Which country has won the most Rugby World Cup titles?", "New Zealand", "Australia", "England", "South Africa", 'a');
                break;

            case 7:
                question15("In which year did the 'Miracle on Ice' occur, when the United States ice hockey team defeated the Soviet Union in the Winter Olympics?", "1980", "1984", "1988", "1992", 'a');
                break;

            case 8:
                question15("Who holds the record for the most career points scored in the National Basketball Association (NBA)?", "LeBron James", "Michael Jordan", "Kobe Bryant", "Kareem Abdul-Jabbar", 'd');
                break;

            case 9:
                question15("In Formula One racing, what does the red flag indicate during a race?", "Race start", "Safety car deployment", "Session suspension", "Race finish", 'c');
                break;

            case 10:
                question15("Who holds the record for the most goals scored in a single season of the UEFA Champions League?", "Lionel Messi", "Cristiano Ronaldo", "Robert Lewandowski", "Raúl González", 'c');
                break;

            case 11:
                question15("In which year did the sport of rugby sevens make its debut at the Olympic Games?", "2000", "2004", "2008", "2012", 'c');
                break;

            case 12:
                question15("Which tennis player has won the most Grand Slam singles titles in the Open Era?", "Roger Federer", "Rafael Nadal", "Serena Williams", "Margaret Court", 'c');
                break;

            case 13:
                question15("Who is the only player to have won the FIFA World Cup, UEFA Champions League, and Ballon d'Or in the same year?", "Lionel Messi", "Cristiano Ronaldo", "Ronaldinho", "Fabio Cannavaro", 'd');
                break;

            case 14:
                question15("In which year was the first modern Olympic Games held?", "1892", "1896", "1900", "1904", 'b');
                break;

            case 15:
                question15("Who holds the record for the most consecutive wins in Formula One?", "Lewis Hamilton", "Michael Schumacher", "Ayrton Senna", "Sebastian Vettel", 'b');
                break;

            case 16:
                question15("Which country has won the most Davis Cup titles in tennis?", "United States", "Australia", "Spain", "France", 'a');
                break;

            case 17:
                question15("Who is the only player to have won the FIFA World Cup, UEFA Champions League, and domestic league titles in England, Spain, and Italy?", "Zinedine Zidane", "Cristiano Ronaldo", "Lionel Messi", "Andrés Iniesta", 'b');
                break;

            case 18:
                question15("In which sport is the term 'knockout' used to describe a match-ending victory?", "Boxing", "Tennis", "Golf", "Badminton", 'a');
                break;

            case 19:
                question15("Who holds the record for the most consecutive NBA MVP (Most Valuable Player) awards?", "LeBron James", "Michael Jordan", "Kareem Abdul-Jabbar", "Bill Russell", 'd');
                break;

            case 20:
                question15("Who holds the record for the fastest 100-meter sprint in athletics?", "Usain Bolt", "Carl Lewis", "Maurice Greene", "Justin Gatlin", 'a');
                break;

            case 21:
                question15("Which country has won the most Olympic gold medals in gymnastics?", "Russia", "China", "United States", "Romania", 'c');
                break;

            case 22:
                question15("Who is the all-time leading scorer in the NBA?", "LeBron James", "Kareem Abdul-Jabbar", "Kobe Bryant", "Michael Jordan", 'b');
                break;

            case 23:
                question15("Which golfer has won the most major championships in history?", "Tiger Woods", "Jack Nicklaus", "Arnold Palmer", "Phil Mickelson", 'b');
                break;

            case 24:
                question15("In which year did the first modern Paralympic Games take place?", "1960", "1976", "1988", "1960", 'd');
                break;
            }



        }

    }
    result();
}

void question15(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaysphard();
}

//MCQS GEOGRAPHY EASY

void displaygeoeasy() //mcqs easy maths
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question16();
}

void display_random_question16()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask16[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask16[no])
        {
            ask16[no] = false;
            switch (no) {
            case 0:
                question16("Which continent is known as the 'Land Down Under'?", "North America", "Africa", "Australia", "Europe", 'c');
                break;

            case 1:
                question16("Which Ocean is the largest in the world?", "Indian Ocean", "Atlantic Ocean", "Pacific Ocean", "Arctic Ocean", 'c');
                break;

            case 2:
                question16("Which country is the largest by land area?", "Russia", "China", "United States", "Canada", 'a');
                break;

            case 3:
                question16("What is the capital city of France?", "Rome", "London", "Paris", "Madrid", 'c');
                break;

            case 4:
                question16("The Great Barrier Reef is located in which country?", "Brazil", "Australia", "Mexico", "Thailand", 'b');
                break;

            case 5:
                question16("What is the longest river in the world?", "Nile River", "Amazon River", "Mississippi River", "Yangtze River", 'a');
                break;

            case 6:
                question16("Mount Everest, the highest peak in the world, is located in which mountain range?", "Andes Mountains", "Rocky Mountains", "Himalayas", "Alps Mountains", 'c');
                break;

            case 7:
                question16("Which country is known as the 'Land of the Rising Sun'?", "China", "Japan", "South Korea", "Thailand", 'b');
                break;

            case 8:
                question16("What is the capital city of Canada?", "Ottawa", "Toronto", "Vancouver", "Montreal", 'a');
                break;

            case 9:
                question16("Which continent is home to the Amazon Rainforest?", "South America", "Africa", "Asia", "Europe", 'a');
                break;

            case 10:
                question16("Which of the following comes among the 7 continents?", "China", "Europe", "Russia", "India", 'b');
                break;

            case 11:
                question16("What is the capital city of Canada?", "Ottawa", "Toronto", "Vancouver", "Montreal", 'a');
                break;

            case 12:
                question16("Which continent is home to the Amazon Rainforest?", "South America", "Africa", "Asia", "Europe", 'a');
                break;

            case 13:
                question16("What is the largest country in South America?", "Brazil", "Argentina", "Colombia", "Peru", 'a');
                break;

            case 14:
                question16("Which desert is the largest in the world?", "Sahara Desert", "Gobi Desert", "Kalahari Desert", "Atacama Desert", 'a');
                break;

            case 15:
                question16("What is the capital city of Russia?", "Moscow", "Saint Petersburg", "Sochi", "Vladivostok", 'a');
                break;

            case 16:
                question16("The Pyramids of Giza are located in which country?", "Greece", "Egypt", "Mexico", "Italy", 'b');
                break;

            case 17:
                question16("Which country is known for its tulips, windmills, and wooden clogs?", "Germany", "France", "Netherlands", "Belgium", 'c');
                break;

            case 18:
                question16("Which city is known as the 'Eternal City'?", "Rome", "Athens", "Paris", "London", 'a');
                break;

            case 19:
                question16("What is the capital city of Australia?", "Sydney", "Melbourne", "Canberra", "Brisbane", 'c');
                break;

            case 20:
                question16("The Great Wall of China is located in which country?", "Japan", "China", "South Korea", "Thailand", 'b');
                break;

            case 21:
                question16("Which continent is the smallest in terms of land area?", "Europe", "Africa", "Australia", "Antarctica", 'd');
                break;

            case 22:
                question16("What is the capital city of Spain?", "Madrid", "Barcelona", "Seville", "Valencia", 'a');
                break;

            case 23:
                question16("Which country has more land area?", "Russia", "America", "India", "China", 'a');
                break;

            case 24:
                question16("Which country has the highest population in the world?", "China", "India", "United States", "Brazil", 'b');
                break;
            }



        }

    }
    result();
}

void question16(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaygeoeasy();
}

//MCQS GEOGRAPHY MEDIUM
void displaygeomed()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question17();
}

void display_random_question17()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask17[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask17[no])
        {
            ask17[no] = false;
            switch (no) {
            case 0:
                question17("What do the letters ‘D’ and ‘C’ stand for in the capital city Washington D.C.?", "District of California", "District of Columbia", "District of Chicago", "District of Canada", 'b');
                break;

            case 1:
                question17("Which is the largest lake in the world?", "Lake Superior", "Lake Victoria", "Caspian Sea", "Great Bear Lake", 'c');
                break;

            case 2:
                question17("Which is the longest river in Africa?", "Nile", "Congo River", "Niger River", "Zambezi River", 'a');
                break;

            case 3:
                question17("Kabul is the capital city of which country?", "Afghanistan", "Iraq", "Pakistan", "Iran", 'a');
                break;

            case 4:
                question17("Which ocean lies between Africa and Australia and south of Asia?", "Atlantic Ocean", "Indian Ocean", "Pacific Ocean", "Arctic Ocean", 'b');
                break;

            case 5:
                question17("What is the color of the motorways on road maps of the UK?", "Red", "Green", "Blue", "Yellow", 'c');
                break;

            case 6:
                question17("Mumbai, Chennai, and Kolkata are metropolitan cities in which country?", "India", "China", "Japan", "Australia", 'a');
                break;

            case 7:
                question17("Europe and Africa are separated by which sea?", "Red Sea", "Baltic Sea", "Mediterranean Sea", "Arabian Sea", 'c');
                break;

            case 8:
                question17("Liverpool lies on which river?", "Thames River", "Rhine River", "Mersey River", "Seine River", 'c');
                break;

            case 9:
                question17("Which desert covers much of northern Africa?", "Gobi Desert", "Sahara Desert", "Kalahari Desert", "Atacama Desert", 'b');
                break;

            case 10:
                question17("Which Italian city is famous for its canals?", "Rome", "Venice", "Florence", "Milan", 'b');
                break;

            case 11:
                question17("In which country does the River Nile meet the sea?", "Sudan", "Egypt", "Kenya", "Tanzania", 'b');
                break;

            case 12:
                question17("What is the largest country in Scandinavia?", "Denmark", "Finland", "Norway", "Sweden", 'd');
                break;

            case 13:
                question17("Which country is the second biggest in the world?", "Russia", "China", "United States", "Canada", 'd');
                break;

            case 14:
                question17("What is the capital city of Spain?", "Madrid", "Barcelona", "Seville", "Valencia", 'a');
                break;

            case 15:
                question17("What is the capital city of Morocco?", "Casablanca", "Marrakech", "Rabat", "Fez", 'c');
                break;

            case 16:
                question17("Mount Everest lies in which mountain range?", "Andes Mountains", "Rocky Mountains", "Himalayas", "Alps Mountains", 'c');
                break;

            case 17:
                question17("Which is the largest country in the world?", "United States", "China", "Russia", "Canada", 'c');
                break;

            case 18:
                question17("What is the hottest continent on Earth?", "North America", "Africa", "South America", "Asia", 'b');
                break;

            case 19:
                question17("Which two continents does Russia belong to?", "Europe and Africa", "Asia and Australia", "Europe and Asia", "North America and Asia", 'c');
                break;

            case 20:
                question17("Where is the biggest railway station in the world?", "London", "Tokyo", "Moscow", "New York City (Grand Central Terminal)", 'd');
                break;

            case 21:
                question17("Dublin is the largest city in which country?", "Ireland", "Scotland", "Wales", "England", 'a');
                break;

            case 22:
                question17("Istanbul is a large city in which country?", "Greece", "Turkey", "Italy", "Egypt", 'b');
                break;

            case 23:
                question17("What is a nickname for New York City?", "The Windy City", "The City of Angels", "The Big Easy", "The Big Apple", 'd');
                break;

            case 24:
                question17("Which place receives the world's highest annual average rainfall?", "Sahara Desert", "Antarctica", "Amazon Rainforest", "Hawaii", 'd');
                break;
            }



        }

    }
    result();
}

void question17(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaygeomed();
}

//MCQS GEOGRAPHY HARD

void displaygeohard()
{
    system("cls");
    cout << "Question NO:" << Q_NO << "\t\tCorrect Answers:" << CORRECT << "\t\tWrong Answers:" << WRONG
        << endl << endl;
    display_random_question18();
}

void display_random_question18()
{
    srand(time(0));
    bool is_question_remaining = false;
    for (int i = 0; i < 25; i++)
    {
        if (ask18[i])
        {
            is_question_remaining = true;
            break;
        }
    }
    while (is_question_remaining && Q_NO <= 10)
    {
        int no = rand() % 25;
        if (ask18[no])
        {
            ask18[no] = false;
            switch (no) {
            case 0:
                question18("What country calls itself Nippon?", "China", "Japan", "Korea", "Thailand", 'b');
                break;

            case 1:
                question18("Which large river flows through London?", "Danube", "Nile", "Thames", "Amazon", 'c');
                break;

            case 2:
                question18("How many bridges are there in Venice, Italy?", "200", "300", "400", "500", 'c');
                break;

            case 3:
                question18("What is the capital of Ethiopia?", "Nairobi", "Cairo", "Addis Ababa", "Lagos", 'c');
                break;

            case 4:
                question18("What is Europe's largest port?", "Port of Rotterdam", "Port of Hamburg", "Port of Antwerp", "Port of Marseille", 'a');
                break;

            case 5:
                question18("Which river flows through Paris?", "River Danube", "River Thames", "River Seine", "River Rhine", 'c');
                break;

            case 6:
                question18("What's the world's biggest port?", "Port of Singapore", "Port of Shanghai", "Port of Rotterdam", "Port of Hong Kong", 'b');
                break;

            case 7:
                question18("Luxembourg City is the capital of which country?", "Luxembourg", "Belgium", "Switzerland", "Austria", 'a');
                break;

            case 8:
                question18("Which American state has the fewest counties?", "Delaware", "Rhode Island", "Vermont", "New Hampshire", 'a');
                break;

            case 9:
                question18("Which Scottish loch with a length of about 24 miles is reputed to contain a monster?", "Loch Lomond", "Loch Ness", "Loch Tay", "Loch Awe", 'b');
                break;

            case 10:
                question18("Where was the greatest difference between annual high and low temperatures recorded?", "Russia", "Australia", "Brazil", "Canada", 'a');
                break;

            case 11:
                question18("Which state in the US was once called Deseret?", "Utah", "Nevada", "Arizona", "New Mexico", 'a');
                break;

            case 12:
                question18("Which island country lies off China, Korea, and Russia?", "Taiwan", "Philippines", "Japan", "Indonesia", 'c');
                break;

            case 13:
                question18("Where is the Tonle Sap located?", "Cambodia", "Vietnam", "Thailand", "Laos", 'a');
                break;

            case 14:
                question18("What is the largest steel arch bridge in the world?", "Golden Gate Bridge", "Sydney Harbour Bridge", "Tower Bridge", "Brooklyn Bridge", 'b');
                break;

            case 15:
                question18("What is Turkey's highest mountain?", "Mount Ararat", "Mount Taurus", "Mount Olympus", "Mount Erciyes", 'a');
                break;

            case 16:
                question18("What is the main tributary of the Ganges River in India?", "Yamuna", "Brahmaputra", "Godavari", "Indus", 'a');
                break;

            case 17:
                question18("Which countries share the longest border in the world?", "USA and Canada", "Russia and China", "Brazil and Argentina", "India and Pakistan", 'a');
                break;

            case 18:
                question18("Which is the largest volcano in the world?", "Mount Kilimanjaro", "Mount Fuji", "Mount Vesuvius", "Mount Lao", 'd');
                break;

            case 19:
                question18("Which country is the most populated in Europe?", "Germany", "France", "United Kingdom", "Italy", 'a');
                break;

            case 20:
                question18("In which country are the holy cities of Mecca and Medina located?", "Iran", "Iraq", "Saudi Arabia", "Kuwait", 'c');
                break;

            case 21:
                question18("What is the line of latitude that runs around the center of the world called?", "Prime Meridian", "Tropic of Capricorn", "Equator", "Arctic Circle", 'c');
                break;

            case 22:
                question18("What is the world's second-highest mountain after Everest in Asia?", "Kanchenjunga", "K2", "Mount Makalu", "Mount Cho Oyu", 'b');
                break;

            case 23:
                question18("In which ocean is the Maldives located?", "Atlantic Ocean", "Indian Ocean", "Pacific Ocean", "Arctic Ocean", 'b');
                break;

            case 24:
                question18("In which ocean is Fiji?", "Atlantic Ocean", "Indian Ocean", "Pacific Ocean", "Arctic Ocean", 'c');
                break;
            }



        }

    }
    result();
}

void question18(string question, string a, string b, string c, string d, char correct_answer)
{
    cout << question << endl;
    cout << "A.\t" << a << endl;
    cout << "B.\t" << b << endl;
    cout << "C.\t" << c << endl;
    cout << "D.\t" << d << endl;
    char answer;
    cin >> answer;
    if (answer == correct_answer)
        CORRECT++;
    else
        WRONG++;
    Q_NO++;
    displaygeohard();
}

//LOGIC OF RESULT and score tracking MCQS QUESTION
void result()
{
    system("cls");
    cout << "Total Question = " << Q_NO - 1 << endl;
    cout << "Correct Answers = " << CORRECT << endl;
    cout << "Wrong Answers = " << WRONG << endl;
    if (CORRECT > WRONG)
        cout << "Result = PASS" << endl;
    else if (WRONG > CORRECT)
        cout << "Result = FAIL" << endl;
    else
        cout << "Result = TIE" << endl;
}

//===========================QUIZZES

//QUIZ Math Easy

void QB_Maths_Easy() {
    string Questions[25] = {
        "The circumference of the circle is also sometimes called:",
        "90 – 35 is equal to:",
        "72 divided by 8 is equal to:",
        "How many sides does a decagon have?",
        "Is -5 an integer? Yes or No.",
        "The value of pi is equal to (in Fractions) :",
        "9 x 7 is equal to:",
        "7^2 is equal to: ",
        "An equilateral triangle has two of its sides equal. True or false?",
        "10 is a natural number. True or false?",
        "-10 is a whole number. True or false?",
        "8 raised to the power 0 is equal to:",
        "The largest 4-digit number is:",
        "The smallest 4-digit number is:",
        "The square of 8 is equal to:",
        "The square root of 5 is (upto 2 decimal places):",
        "3 is a perfect square. True or False?",
        "Cube of 5 is equal to:",
        "What is the value of Pi (up to 3 decimal points)",
        "Cube root of 1331 is:",
        "Is 27 is a perfect cube.?",
        "A square has all its angles equal to how many degrees:",
        "The length of rectangle is 3cm and breadth is 5cm, its area is equal to:",
        "If a is the side of cube, then the volume of the cube is:",
        "A regular polygon has all its sides:"
    };

    string Answers[25] = {
        "perimeter",
        "55",
        "9",
        "10",
        "yes",
        "22/7",
        "63",
        "49",
        "false",
        "true",
        "false",
        "1",
        "9999",
        "1000",
        "64",
        "2.23",
        "false",
        "125",
        "3.147",
        "11",
        "yes",
        "90",
        "15cm",
        "a^3",
        "equal"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}

//QUIZ MATH MEDIUM

void QB_Maths_Med() {
    string Questions[25] = {
        "A number that does not have a numeric of its own.",
        "Name the only even prime number?",
        "What is the perimeter of a circle also called?",
        "What is the actual net number after 7?",
        "53 divided by four is equal to how much?",
        "What is Pi, a rational or irrational number?",
        "Which is the biggest number between 1-9?",
        "How many seconds are there in one day?",
        "How many millimetres are there in one litre?",
        "9*N is equal to 108. What is N?",
        "A image that can also see in three dimensions?",
        "What comes before Quadrillion?",
        "Which number is considered a ‘magical number’?",
        "Which day is Pi day? (mm/dd) ",
        "Who invented the equals to '=' sign?",
        "Initial name for Zero?",
        "Who were the first people to make use of Negative numbers?",
        "Solve the equation: 2x + 5 = 13. ",
        "What is the square root of 64? ",
        "Calculate the area of a rectangle with length 5 units and width 7 units.",
        "Simplify the expression: 3x + 2y - x + 4y. ",
        "What is the product of 8 and 6? ",
        "Solve the equation: 2(x - 3) = 10. ",
        "Calculate the perimeter of a square with side length 9 units. ",
        "What is the Product of 10 and 11?"
    };

    string Answers[25] = {
        "0",
        "2",
        "circumference",
        "11",
        "13",
        "irrational",
        "9",
        "86400",
        "1000",
        "12",
        "hologram",
        "trillion",
        "9",
        "march 14",
        "robert recorde",
        "cipher",
        "chinese",
        "4",
        "8",
        "35 square units",
        "2x + 6y",
        "48",
        "8",
        "36 units",
        "110"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}

//QUIZ MATH HARD


void QB_Maths_Hard() {
    string Questions[25] = {
        "Calculate the value of (12 + 7) x (5 - 3).",
        "Solve for x: 3x + 8 = 20.",
        "Evaluate the expression: √(16 + 9) - 5.",
        "Find the area of a triangle with a base of 6 units and a height of 8 units.",
        "Simplify the expression: 2(3x + 5) - 4(2x - 1).",
        "Calculate the value of 55 raised to the power 5 of 5.",
        "Determine the value of x in the equation: 3x/4 = 6.",
        "Find the perimeter of a rectangle with a length of 50 units and a width of 35 units.",
        "Solve the equation: 2x^2 + 5x - 3 = 0.",
        "Find the value of x in the equation: log(x) + log(x + 3) = 2.",
        "Calculate the value of 6! (factorial).",
        "Simplify the expression: (2/3)^3 ÷ (1/2)^2. (in fraction)",
        "Find the area of a circle with a radius of 5 units.",
        "Solve the equation: e^x = 10. What will be x ? (upto 3 decimal)",
        "Calculate the value of ∫(2x + 3) dx from x = 1 to x = 5.",
        "Add 8.563 and 4.8292.",
        "There is a three-digit number. The second digit is four times as big as the third digit, while the first digit is three less than the second digit. What is the number?",
        "How many feet are in a mile?",
        "What is 1.92÷3",
        "If 72 x 96 = 6927, 58 x 87 = 7885, then 79 x 86 = ?",
        "Look at this series: 36, 34, 30, 28, 24, … What number should come next?",
        "Look at this series: 53, 53, 40, 40, 27, 27, … What number should come next?",
        "What is the highest common factor of the numbers 30 and 132?",
        "What is next in the following number series: 256, 289, 324, 361 . . . ?",
        "At a Christmas party, everyone shook hands with everyone else. There were a total of 66 handshakes that happened during the party. How many people were present? "
    };

    string Answers[25] = {
        "38",
        "4",
        "2",
        "24 square unit",
        "6x + 6",
        "3125",
        "8",
        "170 units",
        "-3",
        "10",
        "720",
        "16/9",
        "78.54 square units",
        "2.302",
        "36",
        "13.3922",
        "141",
        "5280",
        "0.64",
        "6897",
        "22",
        "14",
        "-6",
        "-400",
        "-12"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}

//QUIZ SCIENCE EASY

void QB_Science_Easy() {
    string Questions[25] = {
        "What is the smallest unit of matter ? ",
        "Which is the largest planet of our solar system",
        "What is the chemical symbol for gold? ",
        "Which organ is responsible for pumping blood throughout the body? ",
        "How many planets are there in our solar system? ",
        "Which is the smallest planet of our solar system? ",
        "Which gas makes up the majority of Earth’s atmosphere? ",
        "Water boils at how many degrees Celsius? (",
        "Water freezes at how many degrees Celsius? ",
        "What is the chemical formula for carbon dioxide? ",
        "What is the chemical formula for Salt? ",
        "Salt is also known as? ",
        "How many states of matter are there? ",
        "What is the process by which plants convert sunlight into food? ",
        "What is the largest organ in the human body? ",
        "What is the process by which water changes from liquid to gas? ",
        "What is the SI unit of force? ",
        "What Is the process by which a solid change into a liquid? ",
        "What is the outermost layer of Earth called",
        "What is the pH value of a neutral substance? ",
        "What is the chemical formula of water? ",
        "Which planet is farthest from the sun? ",
        "Which is the 3rd planet in the solar system? ",
        "Which planet is called “red planet”? ",
        "What is the chemical formula for argon? "
    };

    string Answers[25] = {
        "atom",
        "jupiter",
        "au",
        "heart",
        "7",
        "mercury",
        "nitrogen",
        "100",
        "0",
        "co2",
        "nacl",
        "sodium chloride",
        "4",
        "photosynthesis",
        "skin",
        "evaporation",
        "newton",
        "melting",
        "crust",
        "7",
        "h2o",
        "neptune",
        "earth",
        "mars",
        "ar"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}

//QUIZ SCIENCE MEDIUM

void QB_Science_Med() {
    string Questions[25] = {
        "What is the basic unit of life? ",
        "What is the chemical formula for Salt? ",
        "What is the process by which plants convert sunlight into food? ",
        "What is the largest organ in the human body? ",
        "What Is the process by which a solid change into a liquid? ",
        "What is the outermost layer of Earth called",
        "What is the chemical formula for xenon? ",
        "Which planet is called “red planet”? ",
        "Which scientist is famous for his theory of relativity? ",
        "What is the process by which a solid change directly into a gas without becoming a liquid first? ",
        "What is the process by which an unstable atomic nucleus emits radiation? ",
        "Is “Quartz” a type of rock [yes/no] ",
        "What Is the process by which an electric current pass through a gas, causing it to emit light? ",
        "What is the unit of measurement for electric resistance? ",
        "What is responsible for carrying genetic information in cells? ",
        "What is the smallest unit of an element that retains the chemical properties of that element? ",
        "What is the largest organ in the human body by weight? ",
        "What is the SI unit of force? ",
        "Which type of rock is formed from cooled lava or magma? ",
        "What is the unit of measurement for electric current",
        "What is the 2nd largest organ in the human body? (",
        "How many teeth does an adult human have?",
        "How many bones does a child have at birth? ",
        "What is the unit of pressure? ",
        "What is the phenomenon that occurs when light waves change direction as they pass from one medium to another? "
    };

    string Answers[25] = {
        "cell",
        "nacl",
        "photosynthesis",
        "skin",
        "melting",
        "crust",
        "xe",
        "mars",
        "albert einstein",
        "sublimation",
        "radioactivity",
        "no",
        "flourescence",
        "ohm",
        "nucleus",
        "atom",
        "liver",
        "newton",
        "igneous rock",
        "amperes",
        "liver",
        "32",
        "300",
        "pascal",
        "refraction"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}

//QUIZ SCIENCE HARD

void QB_Science_Hard() {
    string Questions[25] = {
        "What is the largest organ in the human body? ",
        "What is the chemical formula for xenon? ",
        "Which scientist is famous for his theory of relativity? ",
        "What is the process by which plants release water vapors in the atmosphere? ",
        "What is the process by which a solid change directly into a gas without becoming a liquid first? ",
        "What is the process by which an unstable atomic nucleus emits radiation? ",
        "What Is the process by which an electric current pass through a gas, causing it to emit light? ",
        "What is the process by which heat is transferred through direct contact between particles of matter? ",
        "____is responsible for carrying genetic information in cells? ",
        "What is the largest organ in the human body by weight?",
        "Which type of rock is formed from cooled lava or magma? ",
        "What is the 3rd largest organ in the human body? ",
        "How many bones does a child have at birth? ",
        "What is the phenomenon that occurs when light waves change direction as they pass from one medium to another? ",
        "What is the process in which atoms split into two or more smaller atoms? ",
        "What Is the process by which plants convert nitrates into nitrogen gas? ",
        "What is the study of Earth’s atmosphere and weather called? ",
        "What is the process by which an organism develops from a fertilized egg? ",
        "What is the study of interactions between organisms and their environment called? ",
        "What is the fourth state of matter? ",
        "Which is the main site of photosynthesis in plant cells? ",
        "Is frictional force a fundamental force of nature? [yes/no] ",
        "What is the process by which a cell divides into two identical daughter cells? ",
        "What is the largest known structure in the universe? ",
        "What is the process in which an organism changes over time in response to its environment? "
    };

    string Answers[25] = {
        "skin",
        "xe",
        "albert einstein",
        "transpiration",
        "sublimation",
        "radioactivity",
        "flourescence",
        "conduction",
        "nucleus",
        "liver",
        "igneous rock",
        "brain",
        "300",
        "refraction",
        "fission",
        "denitrification",
        "meteorology",
        "embryogenesis",
        "ecology",
        "plasma",
        "chloroplast",
        "no",
        "mitosis",
        "supercluster",
        "evolution"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}

//Quiz General knowledge Easy

void QB_Gk_Easy() {
    string Questions[25] = {
        "Which state is famous for Hollywood?",
        "Baby frog is known as?",
        "Name the largest mammal?",
        "Name a bird that lays the largest eggs?",
        "In which capital city of Europe would you find the Eiffel Tower?",
        "Who was the first man to step on the moon?",
        "In sports, what is an MVP?",
        "How many continents are there in the world?",
        "How many bones do sharks have?",
        "Planet closest to the sun",
        "What is a baby sheep called?",
        "Which is the only land animal that cannot jump?",
        "Which is the bird that can fly backward?",
        "Which is the fastest running bird?",
        "Which is the fastest bird?",
        "Which animal can lift 50 times its body weight?",
        "Which Is The largest planet in the solar system? ",
        "How many Earths can fit inside the sun?",
        "How many teeth does an adult human have?",
        "Which is the largest internal organ in the human body? ",
        "How many colors are there in a rainbow?",
        "Which was the first country to use paper money?",
        "Which is the closest star to the Earth?",
        "Which is the largest continent?",
        "From which country did the Statue of Liberty come from?",

    };

    string Answers[25] = {
        "california",
        "tadpole",
        "blue whale",
        "ostrich",
        "paris",
        "neil armstrong",
        "most valuable player",
        "seven",
        "zero",
        "mercury",
        "lamb",
        "elephant",
        "hummingbird",
        "ostrich",
        "falcon",
        "ant",
        "jupiter",
        "1.3 million",
        "32",
        "liver",
        "7",
        "china",
        "sun",
        "asia",
        "france"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}


//Quiz General knowledge Medium

void QB_Gk_Med() {
    string Questions[25] = {
        "How many valves does the heart have?",
        "Which metal has the chemical symbol 'Fe' ? ",
        "Which planet is the hottest in the solar system?",
        "Emerald is the traditional birthstone associated with which month of the year?",
        "Which country produces the most coffee in the world?",
        "What is a group of crows called?",
        "Which gas features predominantly in the earth’s atmosphere, making up roughly 78% of dry air?",
        "What is the largest fruit in the world?",
        "A 'joey' is a baby what?",
        "How Many letters are there in an alphabet?",
        "How many states are there in America?",
        "'For every action, there is an equal and opposite reaction.' Which of Newton’s Laws states this?",
        "Name the tallest type of grass.",
        "How many hearts does a worm have?",
        "Which is the only sport to have been played on the moon?",
        "The world’s tallest building is in which country?",
        "Which is the second-largest country in the world?",
        "In which year did the Titanic sink?",
        "Which has more sugar – a lemon or a strawberry?",
        "What is the color of a giraffe’s tongue?",
        "Which is the shallowest ocean in the world?",
        "Who's credited with inventing the light bulb?",
        "When was the first general-purpose computer invented?",
        "What's a word that's similar to another word called?",
        "How many sides does a hexagon have?"

    };

    string Answers[25] = {
        "4",
        "iron",
        "venus",
        "may",
        "brazil",
        "murder",
        "nitrogen",
        "jackfruit",
        "kangaroo",
        "26",
        "50",
        "newton's 3rd law",
        "bamboo",
        "5",
        "golf",
        "dubai",
        "canada",
        "1912",
        "lemon",
        "black",
        "arctic ocean",
        "thomas edison",
        "1943",
        "synonym",
        "6"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}


//Quiz General knowledge Hard

void QB_Gk_Hard() {
    string Questions[25] = {
        "How many stars are on the Pakistan flag?",
        "In which ocean ‘Bermuda Triangle’ region is Located?",
        "Which country is known as “Land of Rising Sun”?",
        "Which Continent has the largest number of countries?",
        "In which country, largest elephant is found ?",
        "The world’s longest straight road without any corners is located in?",
        "Which is the largest tropical rain forest in the world?",
        "How many countries were participated as a founding member of United Nation?",
        "How many moons does Saturn have?",
        "Who founded Amazon?",
        "Only continent in the world without a desert is.",
        "Total Number of oceans in the world is?",
        "Which country has the greatest number of lakes?",
        "What is the longest bone in the human body?",
        "Smallest bone in the human body?",
        "Which country has the largest Muslim population in the world?",
        "Sultan Ahmed Mosque is in?",
        "How many languages are spoken in Pakistan.",
        "What was the old name of PIA?",
        "Which city is also known as the fruit garden of Pakistan?",
        "Which country is the Largest Producer of Cotton?",
        "Name the driest place on Earth.",
        "When did Pakistan win Olympic gold medal in Hockey for the first time?",
        "How many times did squash player Jansher Khan win the World Open?",
        "Which is the shallowest ocean in the world?"

    };

    string Answers[25] = {
        "1",
        "atlantic",
        "japan",
        "africa",
        "thailand",
        "saudi arabia",
        "amazon",
        "51",
        "124",
        "jeff bezos",
        "europe",
        "5",
        "canada",
        "femur",
        "stapes",
        "indonesia",
        "istanbul",
        "32",
        "orient airways",
        "quetta",
        "india",
        "atacama desert",
        "1960",
        "8",
        "arctic ocean"

    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}



//Quiz English Easy

void QB_Eng_Easy() {
    string Questions[25] = {
        "What is the past tense of the verb 'eat'? ",
        "What is the opposite of the word 'cold'? ",
        "Antonym of 'happy' is ___ ",
        "What would you do if it ___ on your wedding day? ",
        "If she comes, I ___ call you. ",
        "The party has been going on __ two hours ",
        "I haven’t seen her ___ last week ",
        "I haven’t played tennis ___ high school ",
        "Plural form of child is __ ",
        "Which of the following is a verb? [book, table, read]",
        "Which of the following is a noun [run, runner, running] ",
        "Plural of 'mouse' is? ",
        "What is the past participle of the verb 'write'? ",
        "What is the comparative form of the adjective 'good'? ",
        "Superlative degree of 'good'? ",
        "Which of the following is a pronoun [jump, they, dance] ",
        "What is the opposite of 'young'? ",
        "Plural form of 'leaf' ",
        "Which word is a preposition 'the book is on the table'? ",
        "which word is an adverb 'she sings beautifully' ",
        "the book belongs to __ ",
        "Is 'exersise' the correct spelling? [yes/no]",
        "Is 'rhythm' the correct spelling? [yes/no] ",
        "Which of the following is a conjunction [walk, and, quickly] ",
        "Synonym of 'furious' is 'slow' [yes/no] "

    };

    string Answers[25] = {
        "ate",
        "hot",
        "sad",
        "rained",
        "will",
        "for",
        "since",
        "since",
        "children",
        "read",
        "runner",
        "mice",
        "wrote",
        "better",
        "best",
        "they",
        "old",
        "leaves",
        "on",
        "beautifully",
        "them",
        "no",
        "yes",
        "and",
        "no"

    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}


//Quiz English Med

void QB_Eng_Med() {
    string Questions[25] = {
        "She hasn’t been feeling well __ a few days. ",
        "The shop has been closed ___ lunchtime ",
        "She __ a book yesterday ",
        "Which of the following is an adverb [slowly, quick, beautiful] ",
        "Plural form of ‘box’? ",
        "Comparative degree of ‘bad’ ",
        "comparative degree of ‘little’ ",
        "plural form of ‘knife’ ",
        "Plural form of ‘leaf’ ",
        "Which word is a noun [laugh, laughing, laughter] ",
        "Which of the following is a preposition [run, quickly, around, happy] ",
        "the book belongs to __ ",
        "Is ‘necessary’ the correct spelling? [yes/no] ",
        "Is ‘exercise’ the correct spelling? [yes/no] ",
        "Is ‘rhythm’ the correct spelling? [yes/no] ",
        "Plural of ‘ox’ is ‘oxes’ [yes/no] ",
        "Plural form of ‘sheep’ is ",
        "Synonym of ‘persistent’ is ‘determined’ [yes/no] ",
        "As pen is to write, brush is to __ ",
        "Plural of ‘moose’ is ‘mooses’ [yes/no] ",
        "Synonym of ‘excited’ is ",
        "Synonym of ‘vibrant’ is ‘lively’ [yes/no]",
        "‘on’ is a ",
        "‘and’ is a ",
        "Plural of ‘goose’ is ___ "
    };

    string Answers[25] = {
        "for",
        "since",
        "read",
        "slowly",
        "boxes",
        "worse",
        "less",
        "knives",
        "leaves",
        "laughter",
        "around",
        "them",
        "yes",
        "no",
        "no",
        "no",
        "sheep",
        "yes",
        "paint",
        "no",
        "thrilled",
        "yes",
        "preposition",
        "conjunction",
        "geese"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}


//Quiz English Hard

void QB_Eng_Hard() {
    string Questions[25] = {
        "Which word is an adjective [run, running, runner]",
        "Superlative degree of 'bad'?",
        "Superlative degree of 'little'",
        "Which word starts with 'e' and ends with 'e' and has one letter in it?",
        "Which of the following is a preposition [run, quickly, around, happy]",
        "Plural of 'ox' is __",
        "Antonym of expand is",
        "Is 'ecstatic' the correct spelling [yes/no]",
        "As whisper is to speak, tiptoe is to ___",
        "Plural of 'moose' is",
        "As tree is to leaves, flower is to ___",
        "As victory is to triumph, defeat is to ___",
        "Synonym of 'diligent' is",
        "Plural of 'goose' is ___",
        "The team worked ____ (hard) to complete the project",
        "Which of the following is an indefinite pronoun [beautiful, quickly, someone]",
        "Comparative form of 'well' is",
        "Select the word that does not belong to the same category [pen, pencil, eraser, paperclip]",
        "Plural form of 'cactus' is",
        "Plural form of 'elf'",
        "Plural form of 'half' is",
        "Plural form of 'loaf' is",
        "Synonym of 'pensive' is 'cheerful' [yes/no]",
        "The past tense of 'lead' is 'lead' [yes/no]",
        "Plural form of 'analysis' is"
    };

    string Answers[25] = {
        "running",
        "worst",
        "least",
        "envelope",
        "around",
        "oxen",
        "contract",
        "yes",
        "walk",
        "moose",
        "petals",
        "loss",
        "hardworking",
        "geese",
        "hard",
        "someone",
        "better",
        "paperclip",
        "cacti",
        "elves",
        "halves",
        "loaves",
        "no",
        "no",
        "analyses"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }

    resultquiz(Correct_Count, Wrong_Count);
}



//Quiz Sports Easy

void QB_Sports_Easy() {
    string Questions[25] = {
        "What’s the diameter of a basketball hoop in inches?",
        "The Olympics are held every how many years?",
        "Which is the most popular sport?",
        "Which Country introduced cricket?",
        "Which country introduced Football?",
        "In which sport is the Super Bowl the championship game? ",
        "Which sport uses a shuttlecock?",
        "How many players are there in a Football team?",
        "How many players are there in a basketball team?",
        "Which sport is played in a ring called the octagon?",
        "In which sport would you find a goalkeeper?",
        "Which sport is known as 'the gentleman's game'?",
        "How many points is a touchdown worth in American Football?",
        "What is the maximum number of players allowed on a baseball field?",
        "What is the national sport of Canada?",
        "How many stumps are there in a cricket wicket?",
        "What is the duration of a Test match in cricket?",
        "In what game is “love” is a score?",
        "What sport is a lot like softball?",
        "In soccer, what body part can’t touch the ball?",
        "What sporting equipment is used for striking a tennis ball?",
        "Which sport uses a net, a racket, and a shuttlecock?",
        "Which of the following sports does not use a ball? Golf, tennis, boxing, or polo?",
        "What Is the equipment used by Batsman to hit the ball in cricket?",
        "Which sport is played on table with rackets?"
    };

    string Answers[25] = {
        "18 inches",
        "4 years",
        "soccer",
        "england",
        "england",
        "american football",
        "badminton",
        "11",
        "5",
        "mma",
        "football",
        "cricket",
        "6",
        "9",
        "ice hockey",
        "3",
        "5 days",
        "tennis",
        "baseball",
        "hands",
        "tennis racket",
        "badminton",
        "boxing",
        "bat",
        "table tennis"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}

//Quiz Sports Med

void QB_Sports_Med() {
    string Questions[25] = {
        "Which is the second most popular sport in the world?",
        "Which is the third most popular sport in the world?",
        "How many players are there in a cricket team?",
        "What is the highest individual score ever achieved in a Test match?",
        "What is the highest governing body for international cricket?",
        "What is the distance between the two sets of wickets in cricket?",
        "Which country hosted the FIFA World Cup in 2018?",
        "How many people are allowed on the basketball court, per team, in a NBL/NBA game?",
        "Which sport is played on a white surface?",
        "What does a game (score) of table tennis go to?",
        "In soccer, what is it called when you flip over backwards and kick the ball that is over your head?",
        "Which sport is always played in the water?",
        "How many people are allowed on one team on the pitch, at any one time in a professional soccer game?",
        "What was the total number of matches played in the 1975 Cricket World Cup?",
        "Who won the first Cricket World Cup, 1975? ‘",
        "Who won the 1992 Cricket World Cup?",
        "Who was the captain of Pakistan in the Cricket World Cup 1992?",
        "Which country has won the most FIFA World Cups?",
        "Which country has won the most ICC World Cups?",
        "How many FIFA World Cups does Brazil have? ",
        "How many FIFA World Cups does Germany have? ",
        "How much minutes of Extra Time is provided in Football after the full time?",
        "What is scoring 50 runs by a player in cricket called? ",
        "Where is the biggest cricket stadium located?",
        "Who bowled the fastest ball in the history of cricket?"

    };

    string Answers[25] = {
        "cricket",
        "hockey",
        "11",
        "400",
        "icc",
        "22 yards",
        "russia",
        "5",
        "ice hockey",
        "11",
        "bicycle kick",
        "swimming",
        "11",
        "15",
        "west indies",
        "pakistan",
        "imran khan",
        "brazil",
        "australia",
        "5",
        "4",
        "30",
        "half century",
        "melbourne",
        "shoaib akhtar"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}


//Quiz Sports Hard

void QB_Sports_Hard() {
    string Questions[25] = {
        "Who became India's second Grand Master in Chess after Vishwanathan Anand?",
        "What is the beginning level in Karate?	",
        "What is the national sport of India?	",
        "What is the national game of China?",
        "The term Grand Slam is associated with.	",
        "In Volley ball, the number of players on each side is?",
        "The term Googly is associated with which sports?",
        "2014 FIFA World Cup was held in which city?",
        "What is the national game of USA?",
        "The term 'Back-Stroke', 'Breast-Stroke' and 'Butterfly Stroke' are associated with which sports?",
        "The inaugural World Test Cricket Championship took place in 2017 in which country?",
        "A Pugilist is a?",
        "Michael Phelps, who won the highest number of gold medals in Olympic Games in 2008 and 2012, broke the record of?",
        "Number of players in a team of Water Polo is?",
        "'Prince of Wales Cup' is associated with the game of?",
        "The First Asian Games was held in which country?",
        "How many players play in a Kabaddi team?",
        "2018 FIFA World Cup would be held in?",
        "Who is termed as the goat of Football?",
        "Bull Fighting is the national game of which country?",
        "How many seconds of time are professional Golf Tour players allotted per shot?",
        "How many teams does ICC Men's T20 World Cup have?",
        "Which year was the ICC Men's T20 World Cup introduced?",
        "When was Pakistan Super League Introduced?",
        "Which was the latest edition of PSL (Pakistan Super League)?"


    };

    string Answers[25] = {
        "dibyendu barua",
        "white belt",
        "hockey",
        "table tennis",
        "lawn tennis",
        "6",
        "cricket",
        "london",
        "baseball",
        "swimming",
        "england",
        "boxer",
        "mark spitz",
        "7",
        "golf",
        "india",
        "7",
        "russia",
        "cristiano ronaldo",
        "spain",
        "45",
        "20",
        "2007",
        "2015",
        "2023"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}


//Quiz Geography Easy

void QB_Geo_Easy() {
    string Questions[25] = {
        "What is the capital city of France?",
        "What is the largest country in the world by land area?",
        "What is the longest river in the world?",
        "What is the highest mountain in the world? ",
        "What is the capital city of Saudi Arabia?",
        "Which continent is known as the 'Dark Continent'?",
        "What is the largest ocean in the world?",
        "What is the official language of Brazil?",
        "What is the largest desert in the world?",
        "What is the capital city of Canada?",
        "What is the smallest country in the world?",
        "Which country is known as the 'Land of the Rising Sun'? ",
        "What is the official language of Mexico?",
        "What is the largest island in the world?",
        "Which country is famous for the Great Barrier Reef?",
        "What is the capital city of Pakistan?",
        "Which is the largest country in the world by Area?",
        "Which country is known as the 'Land of Fire and Ice'?",
        "What is the official language of China?",
        "What is the largest city in the United States?",
        "Which country is known for the Taj Mahal?",
        "What is the capital city of Spain?",
        "which is the most populated country of the world?",
        "Which country is known for the Pyramids of Giza?",
        "What is the official language of Germany?"



    };

    string Answers[25] = {
        "paris",
        "russia",
        "river nile",
        "mount everest",
        "riyadh",
        "africa",
        "pacific ocean",
        "portuguese",
        "sahara desert",
        "ottawa",
        "vatican city",
        "japan",
        "spanish",
        "greenland",
        "australia",
        "islamabad",
        "russia",
        "iceland",
        "chinese",
        "new york",
        "india",
        "madrid",
        "china",
        "egypt",
        "german"
    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}


//Quiz Geography Medium

void QB_Geo_Med() {
    string Questions[25] = {
        "Which country is home to the Eiffel Tower?",
        "What is the capital city of Argentina?",
        "Which Mountain range is in South America?",
        "What is the official language of South Africa?",
        "Which country is known for its tulips and windmills?",
        "What is the largest city in Canada?",
        "Which African country is known as the 'Pearl of Africa'?",
        "What is the capital city of Thailand?",
        "Which country is known for the Great Wall?",
        "What is the official language of India?",
        "Which continent is known as the 'Land Down Under'?",
        "What is the capital city of Brazil?",
        "Which country is in both Europe and Asia?",
        "What is the official language of Japan?",
        "Which country is known for its fjords?",
        "What is the capital city of Egypt?",
        "Which U.S. state is known as the 'Sunshine State'? ",
        "What is the official language of Nigeria?",
        "Which country is known for the Statue of Liberty?",
        "What is the capital city of Greece?",
        "Which country is famous for its wine production?",
        "What is the official language of Mexico?",
        "Which country is known as the 'Land of the Rising Sun' ? ",
        "What is the capital city of Germany?",
        "Which country is located on the eastern coast of Africa?"



    };

    string Answers[25] = {
        "france",
        "buenos aires",
        "andes mountains",
        "afrikaans",
        "netherlands",
        "toronto",
        "uganda",
        "bangkok",
        "china",
        "hindi",
        "australia",
        "brasilia",
        "turkey",
        "japanese",
        "norway",
        "cairo",
        "florida",
        "english",
        "united states",
        "athens",
        "italy",
        "spanish",
        "japan",
        "berlin",
        "kenya"

    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}


//Quiz Geography Hard

void QB_Geo_Hard() {
    string Questions[25] = {
        "What season does Australia experience in December?",
        "What is the name of the driest continent on Earth?",
        "Peking Duck is the national dish of what country?",
        "In which European city was the first organized marathon held?",
        "What country formerly ruled Iceland?",
        "What is the name of the largest airport in the United States of America?",
        "Which continent is Cambodia located in?",
        "What country is known to have the best quality tap water?",
        "In what ocean is the Bermuda Triangle located?",
        "What city is known as the Glass Capital of the World?",
        "How many stars are on the Australian flag?",
        "Pierre is the capital of what US state?",
        "What is the name of the smallest US state?",
        "What Ocean borders the state of Florida?",
        "What state is Mount Rushmore located in?",
        "What is the name of the largest lake in the US?",
        "In what state would you find the North Mojave Desert?",
        "What is the coldest state in the US?",
        "How many US states share a border with Canada?",
        "What is the largest bay in the US?",
        "What city is the White House located in?",
        "How many time zones are there in the US?",
        "Which US state is known as The Garden State?",
        "What state has the fewest counties?",
        "How many total islands does Hawaii have?"


    };

    string Answers[25] = {
        "summer",
        "antarctica",
        "china",
        "athens",
        "denmark",
        "denver international airport",
        "asia",
        "switzerland",
        "atlantic ocean",
        "toledo",
        "6",
        "south dakota",
        "rhode island",
        "atlantic ocean",
        "south dakota",
        "lake superior",
        "nevada",
        "alaska",
        "13",
        "chesapeake bay",
        "washington dc",
        "6",
        "new jersey",
        "delaware",
        "132"

    };

    int Correct_Count = 0;
    int Wrong_Count = 0;

    srand(time(0));

    for (int i = 0; i < 10; i++) {
        int Random_Index = rand() % (25 - i);
        string question = Questions[Random_Index];
        string Correct_Answer = Answers[Random_Index];

        Questions[Random_Index] = Questions[24 - i];
        Answers[Random_Index] = Answers[24 - i];

        cout << "Question Number: " << (i + 1) << "    Correct Answers: " << Correct_Count << "    Wrong Answers: " << Wrong_Count << endl;
        cout << "--------------------------------------------------------" << endl;
        cout << question << endl;

        string User_Answer;
        cout << "Enter your answer: ";
        cin >> User_Answer;

        if (User_Answer == Correct_Answer) {
            Correct_Count++;
        }
        else {
            Wrong_Count++;
        }

        system("cls");
    }
    resultquiz(Correct_Count, Wrong_Count);
}




//LOGIC OF RESULT and score tracking QUIZ QUESTION
void resultquiz(int correct, int wrong) {
    system("cls");
    cout << "\nTotal Correct Questions = " << correct << endl << endl;
    cout << "Total Wrong Questions = " << wrong << endl << endl;
    if (correct > wrong) {
        cout << "Pass!";
    }
    else if (correct < wrong) {
        cout << "Fail!";
    }
    else {
        cout << "It was a Tie";
    }
}

//======================TRUEFALSE

//TrueFalse Math Easy
void MathsTrueFalseQuizzes() {              //Maths Easy True false
    string questions[25] = {
                "2 + 2 = 5.",
        "The symbol \"+\" means subtraction.",
        "10 is greater than 5.",
        "A square has four sides.",
        "3 multiplied by 4 equals 12.",
        "The number zero is an even number.",
        "1 meter is longer than 1 kilometer.",
        "A triangle has five sides.",
        "10 divided by 2 is equal to 5.",
        "100 is a multiple of 10.",
        "An octagon has eight sides.",
        "20 minutes is equal to 1 hour.",
        "The number one million has six zeroes.",
        "A right angle measures 90 degrees.",
        "7 is an odd number.",
        "A rectangle has two pairs of parallel sides.",
        "The number ten comes after eleven.",
        "The symbol \"÷\" represents addition.",
        "The sum of 6 and 3 is 10.",
        "50 is less than 100.",
        "A hexagon has six sides.",
        "A quarter is equal to 100 cents.",
        "8 multiplied by 0 is equal to 8.",
        "A circle has no sides.",
        "The number 1000 is equal to one million."
    };

    bool answers[25] = {
        false, false, true, true, true, true, false, false, false, true,
        true, false, true, true, true, true, false, false, false, true,
        true, false, true, true, false

    };

    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {                     // generates random questions
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Math Medium

void Maths_MediumTrueFalse() {              //Maths Medium True false
    string questions[25] = {
                "The square root of 144 is 12.",
        "A prime number is divisible by only 1 and itself.",
        "The sum of any two odd numbers is always even.",
        "The value of pi (π) is exactly 3.",
        "Any number raised to the power of zero is equal to one.",
        "A polygon with six sides is called a hexagon.",
        "The commutative property holds true for subtraction.",
        "The equation 3x + 5 = 17 has a solution of x = 4.",
        "Every even number can be expressed as the sum of two prime numbers.",
        "The square root of a negative number is always imaginary.",
        "The angle measures of a triangle always add up to 180 degrees.",
        "An irrational number can be written as a fraction.",
        "The absolute value of -5 is greater than the absolute value of -3.",
        "The equation 2x + 3y = 10 represents a linear relationship.",
        "The hypotenuse of a right triangle is always the longest side.",
        "The number zero is considered neither positive nor negative.",
        "A decimal fraction can always be expressed as a repeating or terminating decimal.",
        "A right triangle can never be isosceles.",
        "The sum of any two irrational numbers is always irrational.",
        "The equation x^2 - 4 = 0 has no real solutions.",
        "In a parallelogram, opposite angles are equal in measure.",
        "A function can have multiple outputs for the same input.",
        "The number e is an irrational number.",
        "A scalene triangle has all sides of equal length.",
        "The product of any number and zero is always zero."
    };

    bool answers[25] = {
         true, true, false, false, true, true, false, true, false, true,
        true, false, false, true, true, true, false, false, false, false,
        true, false, true, false, true
    };

    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Math Hard

void Maths_HardTrueFalse() {              //Maths Hard True false
    string questions[25] = {
                 "The number 0.999... is equal to 1.",
        "Every prime number greater than 2 is odd.",
        "The sum of an infinite geometric series always converges to a finite value.",
        "The square root of 2 is a rational number.",
        "The equation x^3 + y^3 = z^3 has integer solutions for x, y, and z.",
        "The derivative of a constant function is always zero.",
        "The interior angles of a regular pentagon add up to 540 degrees.",
        "The number 0.999... is a repeating decimal.",
        "There are infinitely many prime numbers.",
        "The sum of the reciprocals of the prime numbers diverges.",
        "The equation e^x = x has a solution.",
        "The sum of an arithmetic series can be written as (n/2)(a + l), where n is the number of terms, a is the first term, and l is the last term.",
        "The tangent function is periodic with a period of 180 degrees.",
        "The Fibonacci sequence is an example of a geometric sequence.",
        "The set of irrational numbers is countable.",
        "The factorial of a negative integer is defined.",
        "The derivative of sin(x) is cos(x^2).",
        "The number pi (π) is a rational number.",
        "The integral of a continuous function over a closed interval always exists.",
        "The sum of the angles of a triangle in hyperbolic geometry is less than 180 degrees.",
        "A square matrix is invertible if and only if its determinant is nonzero.",
        "The harmonic series, 1 + 1/2 + 1/3 + 1/4 + ..., converges.",
        "The series 1 - 1 + 1 - 1 + 1 - 1 + ... is convergent.",
        "The limit of a function exists if and only if the left-hand limit and right-hand limit exist and are equal.",
        "The Cantor set has a measure of zero."
    };

    bool answers[25] = {
         true, true, true, false, false, true, false, true, true, true,
        true, true, false, false, false, false, false, false, true, true,
        true, false, false, true, true
    };

    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {                //generated random questions
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Science Easy

void Science_EasyTrueFalse() {              //Science Easy True false
    string questions[25] = {
                "Earth is the largest planet in the solar system",
        "Water boils at 100 degrees Celsius",
        "Humans only use 10% of their brain",
        "The sun revolves around the earth",
        "Matter exists in 3 states",
        "Gravity of earth is stronger than on moon",
        "All metals are magnetic",
        "Human skeleton is made up of 206 bones",
        "All elements in the periodic table are naturally occurring",
        "The periodic table has 118 elements",
        "All bacteria are harmful to humans",
        "The process of evaporation involves the conversion of a liquid into a gas",
        "Molecules are made up of atoms bonded together",
        "All forms of energy can be replaced",
        "The skin is the largest organ in the human body",
        "All elements in the periodic table have isotopes",
        "The human body is composed mostly of water",
        "UV radiation is visible to the human eye",
        "All elements in the periodic table have stable isotopes",
        "All living organisms are composed of cells",
        "All acids have sour taste",
        "All species on Earth have been discovered and named",
        "All substances expand when frozen",
        "All matter is composed of atoms",
        "All chemical reactions involve the exchange of atoms"
    };

    bool answers[25] = {
          false, true, false, false, false, true, false, true, false, true,
        false, true, true, false, true, true, false, false, true, true,
        false, false, false, true, true
    };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Science Medium

void Science_MediumTrueFalse() {              //Science Medium True false
    string questions[25] = {
                "Water boils at 100 degrees Fahrenheit",
        "The process of photosynthesis only occurs in plants",
        "All living organisms require oxygen to survive",
        "Human body can survive on one kidney",
        "All chemical reactions release energy",
        "The process of diffusion only occurs in gases",
        "Black holes are empty regions of space with no matter",
        "All fungi are plants",
        "The skin is the largest organ in the human body",
        "The earth’s magnetic field is generated by the core of molten iron",
        "All elements in the periodic table have isotopes",
        "The human body is composed mostly of water",
        "Virus is considered living organisms",
        "All chemical reactions occur at the same rate",
        "All substances expand when heated",
        "All mammals lay eggs",
        "All chemical reactions are reversible",
        "All living organisms are composed of cells",
        "All elements in the periodic table have stable isotopes",
        "All living organisms are composed of cells",
        "All electromagnetic waves travel at same speed",
        "All acids have sour taste",
        "All chemical reactions involve the exchange of atoms",
        "All substances expand when frozen",
        "All minerals are inorganic substances"
    };

    bool answers[25] = {
          false, false, false, true, false, false, false, false, true, true,
        true, true, false, false, false, false, true, true, false, true,
        true, false, true, false, true
    };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}



//TrueFalse Science Hard

void Science_HardTrueFalse() {              //Science Hard True false
    string questions[25] = {
            "Atomic number of oxygen is 8",
        "All acids are corrosive",
        "Ozone layer is in the Earth’s inner core",
        "The primary source of energy for the sun is nuclear fusion",
        "Energy can be created and destroyed",
        "The skin is the largest organ in the human body",
        "A light-year is a measure of time",
        "The earth’s magnetic field is generated by the core of molten iron",
        "All elements in the periodic table have isotopes",
        "Virus is considered living organisms",
        "All planets in the solar system have moons",
        "All cells in a human body contain a nucleus",
        "All chemical reactions are reversible",
        "All elements heavier than iron are created in supernovae",
        "All living organisms are composed of cells",
        "All electromagnetic waves travel at the same speed",
        "All acids have a sour taste",
        "All minerals are inorganic substances",
        "All chemical reactions involve the exchange of atoms",
        "All species of snakes are venomous",
        "All elements in the periodic table can form stable compounds with other elements",
        "All clouds in the atmosphere contain water droplets",
        "Nucleus is responsible for carrying genetic information in cells",
        "pH value of a neutral substance is 0",
        "Nitrogen is a greenhouse gas"
    };

    bool answers[25] = {
         true, false, false, true, false, true, false, true, true, false,
        false, false, true, true, true, true, false, true, true, false,
        false, false, true, false, true
    };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}



//TrueFalse GeneralKnowledge Easy

void GeneralKnowledgeTrueFalse() {
    string questions[25] = {
        "The longest river in the world is the Amazon River.",
        "Polar bears can only live in the Arctic region, not in the Antarctic.",
        "The United Kingdom is almost the same size as France.",
        "The moon is wider than Australia.",
        "The goat is used to symbolize the zodiac sign, Capricorn.",
        "In a regular deck of cards, all kings have a mustache.",
        "There is no English word that rhymes with orange.",
        "The mosquito has a record for killing more people than any other species in written history.",
        "Bananas are curved due to their upward growth toward the light.",
        "When the two numbers on opposite sides of the dice are added together, the result is always 7.",
        "When going out of the cave, the bats always turn in the right direction.",
        "Among the letters of the alphabet, only the letter J is not included in the periodic table.",
        "The first living animal sent into space were fruit flies.",
        "English is one of the official languages of the Philippines.",
        "South Africa officially has three capital cities.",
        "Corn is the most widely cultivated and consumed crop on the planet.",
        "The Pacific Ocean is the world's biggest ocean.",
        "Nepal is the only country in the world without a rectangular flag.",
        "The letter 'E' is the most commonly used in the English language.",
        "Switzerland's currency is the Euro.",
        "Canada has the longest coastline in the world.",
        "The Philippines is an archipelagic country that has the most number of islands.",
        "The number of bones in an infant is more than that of an average human.",
        "The liver is the largest internal organ in the human body.",
        "The human brain contains the maximum amount of muscle density."
    };

    bool answers[25] = { false, true, false, false, true, false, true, true, true, true, false, true, true, true, true, true, false, true, false, true, false, true, false, true, false };


    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse GeneralKnowledge Med

void GeneralKnowledgeMediumTrueFalse() {
    string questions[25] = {
         "The tongue is the only part of the human body with taste buds.",
        "The human eyes can observe 10 million different colors.",
        "The average human body consists of 60% water.",
        "Sharks are categorized as mammals.",
        "The blue whale is the biggest known animal to have ever existed.",
        "An ant can lift 2000 times its body weight.",
        "In the US, pepperoni is the most widely used pizza topping.",
        "French fries are a French invention.",
        "There are always even numbers of rows on corn ears.",
        "By the number of locations, McDonald’s has the most eateries in the US.",
        "In terms of land area, Polo occupies the most space.",
        "The same amount of dimples appears on each golf ball.",
        "In 1943, helmet use among football players began.",
        "Brazil is the only country to have participated in each World Cup finals match.",
        "The biggest marathon in the world is the one in New York.",
        "On the moon, an astronaut once played golf.",
        "Compared to a hydrogen atom, a carbon atom is lighter.",
        "Bats are blind.",
        "Greenland is the largest island in the world.",
        "The most common blood type is O-negative.",
        "Is Lisbon the capital of Portugal?",
        "Is the sparrow the smallest bird?",
        "The construction of the Eiffel Tower was completed on March 31, 1887.",
        "Lightning is seen before it's heard because light travels faster than sound.",
        "Is Melbourne the capital of Australia?"
    };
    bool answers[25] = { false, true, true, false, true, false, true, false, true, false, true, false, true, true, true, true, false, false, true, true, true, false, false, true, true };


    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse GeneralKnowledge Hard

void GeneralKnowledgeHardTrueFalse() {
    string questions[25] = {
        "Mount Fuji is the highest mountain in Japan.",
        "Broccoli contains more vitamin C than lemons.",
        "The skull is the strongest bone in the human body.",
        "Light bulbs were the invention of Thomas Edison.",
        "Google was initially called BackRub.",
        "Mercury's atmosphere is made up of Carbon Dioxide.",
        "Depression is the leading cause of disability worldwide.",
        "Cleopatra was of Egyptian descent.",
        "The skull is the strongest bone in the human body.",
        "You can sneeze while asleep.",
        "It's impossible to sneeze while you open your eyes.",
        "Bananas are berries.",
        "If you add the two numbers on the opposite sides of the dice together, the answer is always 7.",
        "Scallops can't see.",
        "A snail can sleep up to 1 month.",
        "Your nose produces almost one liter of mucus a day.",
        "Mucus is healthy for your body.",
        "Coca-Cola exists in every country around the world.",
        "Spider silk was once used to make guitar strings.",
        "A coconut is a nut.",
        "A chicken can live without a head long after it's chopped off.",
        "Humans share 95 per cent of their DNA with bananas.",
        "Giraffes say 'moo'.",
        "In Arizona, USA, you can get sentenced for cutting down a cactus.",
        "In Ohio, USA, it is illegal to get a fish drunk."
    };
    bool answers[25] = {
            true, true, false, false, true, false, true, false, false, false, true, true, true, false, false, true, true, false, false, false, true, false, true, true, false
    };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse English Easy

void EnglishEasyTrueFalse() {
    string questions[25] = {
         "A plural subject needs a plural verb.",
        "The past tense of the verb 'eat' is 'eaten'.",
        "The opposite of the word 'cold' is 'hot'.",
        "Every sentence must have a subject and an adverb.",
        "The synonym of 'furious' is 'calm'.",
        "An adjective is used to describe a verb.",
        "A conjunction is used to connect words, phrases, or clauses.",
        "An adverb modifies a verb, adjective, or other adverbs.",
        "A pronoun is a word used to replace a noun.",
        "A simile is a figure of speech that compares two things using 'like' or 'as'.",
        "'Founded' is the past tense of 'Found'.",
        "'Equivalent To' is the same as 'Equal To'.",
        "Is 'necessary' the correct spelling?",
        "Is the sentence correct: 'I was went to the store yesterday'?",
        "Is the sentence correct: 'Our neighbor used smoking a pipe'?",
        "The past tense of 'run' is 'runned'.",
        "Is 'receive' the correct spelling?",
        "'Run' is an adverb.",
        "'On' is a preposition.",
        "Is the sentence correct: 'Have you ever go to Hollywood'?",
        "The comparative form of 'good' is 'more good'.",
        "The synonym of 'brave' is 'courageous'.",
        "The synonym of 'furious' is 'slow'.",
        "The plural of 'mouse' is 'mouses'.",
        "The synonym of 'excited' is 'thrilled'."
    };

    bool answers[25] = { true, false, true, false, false, false, true, true, true, true, true, true, true, false, false, false, true, false, true, false, false, true, false, false, true };

    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse English Medium

void EnglishMediumTrueFalse() {
    string questions[25] = {
          "A metaphor is a figure of speech that compares two things using 'like' or 'as'.",
        "A compound sentence contains two or more independent clauses.",
        "A possessive pronoun shows ownership or possession.",
        "The past tense of 'Find' is 'Found'.",
        "The comparative form of 'good' is 'better'.",
        "The comparative form of 'bad' is 'badly'.",
        "Is the sentence correct 'I have always been to Paris'?",
        "The synonym of 'vibrant' is 'lively'.",
        "The antonym of 'brave' is 'fearful'.",
        "The plural of 'mouse' is 'mice'.",
        "The plural of 'sheep' is 'sheeps'.",
        "The synonym of 'excited' is 'worried'.",
        "The synonym of 'persistent' is 'determined'.",
        "The correct spelling is 'broccoli'.",
        "The correct spelling is 'manouver'.",
        "Is the sentence correct 'I've already eaten lunch'?",
        "The plural of 'moose' is 'moose'.",
        "Is 'exhilirate' the correct spelling?",
        "The synonym of 'pensive' is 'thoughtful'.",
        "As pen is to write, brush is to wash.",
        "Is the sentence correct 'The cat is sleeping below the couch'?",
        "As tree is to leaves, flower is to petals.",
        "As book is to read, movie is to act.",
        "Is 'pursue' the correct spelling?",
        "The antonym of 'excited' is 'apathetic'."
    };


    bool answers[25] = { false, true, true, true, true, false, false, true, true, true, false, false, true, true, false, true, true, false, true, false, false, true, false, true, true };

    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse English Hard

void EnglishHardTrueFalse() {
    string questions[25] = {
           "Is 'persue' the correct spelling?",
        "The synonym of 'diligent' is 'gloomy'.",
        "The correct spelling is 'indecisive'.",
        "The antonym of 'expand' is 'contract'.",
        "Is 'ecstatic' the correct spelling?",
        "The correct spelling is 'maneuver'.",
        "The antonym of 'subtle' is 'discreet'.",
        "The synonym of 'subtle' is 'elusive'.",
        "The plural of 'moose' is 'mooses'.",
        "The synonym of 'pensive' is 'cheerful'.",
        "As tree is to leaves, flower is to roots.",
        "The synonym of 'ephemeral' is 'transient'.",
        "The antonym of 'ephemeral' is 'brief'.",
        "The synonym of 'excited' is 'agog'.",
        "The past participle of 'enthrall' is 'enthrall'.",
        "The word 'onomatopoeia' refers to words that imitate the sounds they describe.",
        "Is 'irregardless' a correct word?",
        "An adverb can modify a noun in a sentence.",
        "The words 'affect' and 'effect' are always interchangeable.",
        "The word 'their' is always a possessive pronoun.",
        "The word 'inflammable' is always the same as 'non-flammable'.",
        "Double negatives in a sentence are grammatically incorrect in English.",
        "The past tense of 'lead' is 'lead'.",
        "The term 'oxymoron' refers to a figure of speech that combines contradictory terms.",
        "The word 'fast' can both be an adjective and an adverb."
    };


    bool answers[25] = { false, false, true, true, true, true, false, true, false, false, false, true, false, true, false, true, false, false, false, true, true, false, false, true, true };


    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Sports Easy

void SportsEasyTrueFalse() {
    string questions[25] = {
              "In cricket, the bowler throws the ball to the batsman.",
    "A football match consists of two halves of 45 minutes each.",
    "In badminton, the shuttlecock is hit over the net with a racket.",
    "In hockey, players use a stick to hit the ball into the goal.",
    "A cricket team can score 5 runs with a single shot.",
    "The goalkeeper is the only player allowed to touch the ball with their hands in football.",
    "In badminton, a match is played with a shuttlecock made of feathers.",
    "Hockey matches consist of two halves of 30 minutes each.",
    "In cricket, the fielding team has 11 players on the field.",
    "In football, a penalty kick is awarded when a player commits a foul inside their own penalty area.",
    "Badminton is played with a ball instead of a shuttlecock.",
    "Hockey is played on a rectangular field called a pitch.",
    "In cricket, the wickets are made of wood.",
    "A football match can end in a draw if both teams score the same number of goals.",
    "In badminton, players score points by hitting the shuttlecock into the opponent's net.",
    "In hockey, a penalty corner is awarded when a defender commits a foul inside their own circle.",
    "In cricket, a batsman is out if the fielding team catches the ball before it touches the ground.",
    "In football, a yellow card is shown to a player as a warning for committing a foul.",
    "A badminton match consists of three sets.",
    "In hockey, a goal is scored when the ball crosses the goal line between the goalposts and under the crossbar.",
    "In cricket, the batting team tries to score runs by running between the wickets.",
    "In football, a free kick is awarded to the opposing team when a player commits a handball.",
    "A badminton racket is smaller in size compared to a tennis racket.",
    "In hockey, the goalkeeper wears protective gear, including pads and a helmet.",
    "In cricket, a match can last for multiple days."

    };


    bool answers[25] = {
   false, true, true, true, false, true, true, true, true, true,
   false, true, true, true, false, true, true, false, true, false,true, true, true, true, true };

    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Sports Medium

void SportsMediumTrueFalse() {
    string questions[25] = {
              "In cricket, a team can win a match without scoring a single run.",
        "In football, the referee can show a red card without issuing a yellow card first.",
        "A badminton match can end in a tie.",
        "In hockey, a goal can be scored directly from a hit-in.",
        "In cricket, the maximum number of runs that can be scored in a single ball is 8.",
        "In football, a player can score a goal directly from a throw-in.",
        "A badminton shuttlecock weighs less than a tennis ball.",
        "In hockey, a player can use their feet to stop the ball.",
        "In cricket, a batsman can be out even if the ball hits their helmet.",
        "In football, a player can score a goal directly from a corner kick.",
        "A badminton match can have a time limit.",
        "In hockey, the goalkeeper is allowed to leave the goal area.",
        "In cricket, a batsman can be given out for obstructing the field.",
        "In football, the offside rule does not apply to throw-ins.",
        "A badminton match can have more than two players on each side.",
        "In hockey, a player can be given a penalty for raising their stick above the shoulder.",
        "In cricket, a batsman can be given out if the ball bounces twice before reaching them.",
        "In football, the goalkeeper cannot be substituted during a match.",
        "A badminton match can have more than one shuttlecock in play.",
        "In hockey, a player can use their body to intentionally block the ball.",
        "In cricket, a six can be scored even if the ball does not touch the ground.",
        "In football, a player can be offside from a goal kick.",
        "A badminton rally can consist of more than 100 shots.",
        "In hockey, a player can be given a penalty for deliberately playing the ball with their feet.",
        "In cricket, a bowler can bowl consecutive overs without any limit."
    };


    bool answers[25] = {
 false, true, false, false, false, false, true, true, false, true,
  true, false, true, true, false, true, true, false, false, true,
 true, false, true, true, false };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Sports Hard

void SportsHardTrueFalse() {
    string questions[25] = { "In cricket, a batsman can be given out for obstructing the field, even if there is no intention to do so.",
        "In football, a player can be given a red card for using offensive language towards the referee.",
        "In badminton, a player cannot touch the net with their racket during a rally without committing a fault.",
        "In hockey, a team can score a goal directly from a free hit awarded outside the shooting circle.",
        "In cricket, a bowler can be penalized for bowling consecutive bouncers.",
        "In football, a player cannot be called offside if they are in their own half when the ball is played.",
        "In badminton, a player cannot win a rally by hitting the shuttlecock into the opponent's side wall.",
        "In hockey, a goalkeeper can score a goal directly from a penalty corner.",
        "In cricket, a batsman can be given out for handling the ball even if it is unintentional.",
        "In football, a player cannot receive a yellow card for excessive celebration after scoring a goal.",
        "In badminton, a player cannot touch the net with their body during a rally without committing a fault.",
        "In hockey, a player can play the ball while lying on the ground.",
        "In cricket, a bowler can be penalized for bowling a ball with an illegal action.",
        "In football, a team can be awarded a goal if the opposing team commits a deliberate handball on the goal line.",
        "In badminton, a player cannot use their feet to return the shuttlecock.",
        "In hockey, a player can deliberately lift the ball above shoulder height during a match.",
        "In cricket, a batsman can be given out for leaving their crease before the bowler has delivered the ball.",
        "In football, a player can be given a red card for diving to simulate a foul.",
        "In badminton, a player can request a time-out during a match.",
        "In hockey, a team can substitute their goalkeeper with an outfield player during a match.",
        "In cricket, a bowler can be given a no-ball for bowling a ball above waist height.",
        "In football, a player can receive a yellow card for removing their shirt during a goal celebration.",
        "In badminton, a player can request to change the shuttlecock if they find it damaged.",
        "In hockey, a team can score a goal directly from a hit-in taken from the sideline.",
        "In cricket, a batsman can be given out for obstructing the field by deliberately running in a straight line to block the fielder's throw."
    };


    bool answers[25] = { true, true, true, false, false, true, true, true, true, false, true, true, true, true, true, false, true, true, true, true, false, true, true, true, true
    };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Geography Easy

void GeographyEasyTrueFalse() {
    string questions[25] = { "The capital of Australia is Sydney.",
    "The Nile River is the longest river in the world.",
    "Mount Everest is the tallest mountain in the world.",
    "Brazil is the largest country in South America.",
    "The Great Wall of China can be seen from space.",
    "The Sahara Desert is the largest desert in the world.",
    "The Eiffel Tower is located in London.",
    "Antarctica is the coldest continent on Earth.",
    "Japan is an island country.",
    "The Amazon Rainforest is located in Africa.",
    "The Statue of Liberty is located in New York City.",
    "The Caribbean Sea is located in the Pacific Ocean.",
    "The Taj Mahal is located in India.",
    "The Arctic is the smallest ocean in the world.",
    "Mount Kilimanjaro is located in Kenya.",
    "Australia is both a country and a continent.",
    "The Colosseum is located in Rome, Italy.",
    "The Grand Canyon is located in Colorado.",
    "The Great Barrier Reef is located in Australia.",
    "The Andes Mountains are the longest mountain range in the world.",
    "The Great Lakes are located in Africa.",
    "The capital of France is London.",
    "The Gobi Desert is located in Africa.",
    "The Nile River flows through Egypt.",
    "Mount Fuji is located in China."
    };

    bool answers[25] = { false, true, true, true, false, true, false, true, true, false, true, false , true, false, false, true, true, false, true, true, false, false, true, false, false };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Geography Medium
void GeographyMediumTrueFalse() {
    string questions[25] = {
        "The Tropic of Cancer passes through South America.",
        "The Dead Sea is the saltiest body of water on Earth.",
        "The capital of Canada is Toronto.",
        "The Galapagos Islands are part of Ecuador.",
        "The Great Barrier Reef is the largest coral reef system in the world.",
        "The capital of China is Shanghai.",
        "The Rocky Mountains are located in Europe.",
        "The Great Dividing Range is the main mountain range in New Zealand.",
        "The city of Moscow is located in Asia.",
        "The Atacama Desert is the driest desert in the world.",
        "The Danube River is the longest river in Europe.",
        "The city of Cape Town is located in South Africa.",
        "The Great Wall of China is over 10,000 miles long.",
        "The country of Peru is located in Central America.",
        "The island of Madagascar is located in the Indian Ocean.",
        "The capital of Italy is Rome.",
        "The Ganges River is considered sacred by Hindus.",
        "The Outback is a term used to describe the remote interior regions of Australia.",
        "The Andaman Islands are part of Indonesia.",
        "Mount Vesuvius is a volcano in Greece.",
        "The city of Istanbul is located on two continents.",
        "The Serengeti National Park is located in Kenya.",
        "The country of Chile has a coastline along the Pacific Ocean.",
        "The city of Sydney is the capital of Australia.",
        "The Alps are the highest mountain range in Africa."
    };

    bool answers[25] = { false,true,false,true,true,false,false,false,true,true,true,true,true,false,true, true,true,true,false,false,true,false,true,false, false };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//TrueFalse Geography Hard

void GeographyHardTrueFalse() {
    string questions[25] = {
      "The Mekong River flows through Cambodia.",
        "The Great Dividing Range is the longest mountain range in Australia.",
        "The Strait of Gibraltar separates Europe and Africa.",
        "The city of Auckland is located in New Zealand's North Island.",
        "The Kalahari Desert is located in Southern Africa.",
        "The Rhine River flows through Switzerland.",
        "The city of Reykjavik is the capital of Iceland.",
        "The Rocky Mountains span several US states, including Colorado and Wyoming.",
        "The city of Rio de Janeiro is located in Brazil's state of Sao Paulo.",
        "The Great Victoria Desert is the largest desert in Australia.",
        "The city of Buenos Aires is the capital of Argentina.",
        "The Carpathian Mountains are located in Eastern Europe.",
        "The city of Lima is the capital of Peru.",
        "The Amazon River is the longest river in South America.",
        "The city of Istanbul is located on the Bosphorus Strait.",
        "The Himalayas are the highest mountain range in the world.",
        "The city of Cape Town is located in South Africa.",
        "The Amazon Rainforest is primarily located in Brazil.",
        "The city of Sydney is the capital of Australia.",
        "The Great Barrier Reef is the largest coral reef system in the world.",
        "The city of Bangkok is the capital of Thailand.",
        "The Ural Mountains separate Europe and Asia.",
        "The city of Vancouver is located in the province of Alberta.",
        "The Atacama Desert is located in Chile.",
        "The city of Moscow is the capital of Russia."
    };

    bool answers[25] = { true,true,true,true,true,false, true,true,false,false, true,true,true,true,true,true,true,true,false,true,true,true,false,true,true
    };
    int correctCount = 0;
    int wrongCount = 0;

    srand(time(0));

    bool asked[25] = { false }; // Flag array to track asked questions

    for (int i = 0; i < 10; i++) {
        int randomIndex;
        do {
            randomIndex = rand() % 25;
        } while (asked[randomIndex]); // Repeat until a unique question is found

        asked[randomIndex] = true; // Mark the question as asked

        string question = questions[randomIndex];

        cout << "Question Number: " << (i + 1) << "     Correct Answers: " << correctCount << "     Wrong Answers: " << wrongCount << std::endl;
        cout << "-------------------------------------------------------------" << endl;
        cout << question << endl;

        bool userAnswer;
        cout << "\nEnter your answer (0 for False, 1 for True): ";
        cin >> userAnswer;

        if (userAnswer == answers[randomIndex]) {
            cout << "Correct answer!" << endl;
            correctCount++;
        }
        else {
            cout << "Wrong answer!" << endl;
            wrongCount++;
        }

        // Clear the input buffer
        cin.clear();
        while (cin.get() != '\n') {
            continue;
        }
        system("cls");
    }
    resulttrue(correctCount, wrongCount);
}


//LOGIC OF RESULT and score tracking True False QUESTION

void resulttrue(int correct, int wrong) {                   //result total output
    system("cls");
    cout << "\nTotal Correct Questions = " << correct << endl << endl;
    cout << "Total Wrong Questions = " << wrong << endl << endl;
    if (correct > wrong) {
        cout << "Pass!";
    }
    else if (correct < wrong) {
        cout << "Fail!";
    }
    else {
        cout << "It was a Tie";
    }

}

