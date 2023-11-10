# ByteBuster-Quiz-Game

#include <iostream>
using namespace std;
#include <cstdlib>
#include<list>
#include<stack>

struct Question {
    string questionText;
    list<string> options;  
int correctOption;
};

struct User {
    string name;
     int age;
      int score;
};

void welcomePage() {
    cout << "Welcome to ByteBuster Quiz!" << std::endl;
cout << "Press Enter to start the quiz...";
cin.ignore(); 
    system("clear");  
}
User getUserInfo() {
    User user;
     cout << "Enter your name: ";
    cin >> user.name;
cout << "Enter your age: ";
    cin >> user.age;
return user;
}

bool askToPlay(User user) {
    cout << "Hello, " << user.name << "!! Do you want to play the quiz? (yes/no): ";
    string response;
    cin >> response;

    if (response == "no") {
        cout << "Thank you for coming, " << user.name << "!" << endl;
        cout << "Goodbye! Have a great day." << endl;
        exit(0); // Exit the program
    } else if (response == "yes") {
        return true; // Start the quiz
    } else {
        cout << "Invalid response. Please enter 'yes' or 'no'." << endl;
        return askToPlay(user); // Ask the question again if the response is neither 'yes' nor 'no'
    }
}





list<Question> loadQuestionsForLevel1() {
    list<Question> questions;  
Question q1 = {
        "Who invented C++?",
        {"a) Dennis Ritchie", "b) Ken Thompson", "c) Brian Kernighan", "d) Bjarne Stroustrup"},
        4
    };
Question q2 = {
        "What is C++?",
        {"a) C++ is an object-oriented programming language", "b) C++ is a procedural programming language", "c) C++ supports both procedural and object-oriented programming language", "d) C++ is a functional programming language"},
        3
    };

Question q3 = {
        "Which of the following is the correct syntax of including a user-defined header file in C++?",
        {"a) #include [userdefined]", "b) #include “userdefined”", "c) #include <userdefined.h>", "d) #include <userdefined>"},
        2
    };

     Question q4 = {
        "Which of the following is used for comments in C++?",
        {"a) /* comment */", "b) // comment */", "c) // comment", "d) both // comment or /* comment */"},
        4
    };

 Question q5 = {
        "Which of the following user-defined header file extensions is used in C++?",
        {"a) hg", "b) cpp", "c) h", "d) hf"},
        3
    };

      Question q6 = {
        "Which of the following is a correct identifier in C++?",
        {"a) VAR_1234", "b) $var_name", "c) 7VARNAME", "d) 7var_name"},
        1
    };

      Question q7 = {
        "Which of the following is not a type of Constructor in C++?",
        {"a) Default constructor", "b) Parameterized constructor", "c) Copy constructor", "d) Friend constructor"},
        4
    };

Question q8 = {
        "Which of the following approaches is used by C++?",
        {"a) Left-right", "b) Right-left", "c) Bottom-up", "d) Top-down"},
        3
    };

Question q9 = {
        "What is virtual inheritance in C++?",
        {"a) C++ technique to enhance multiple inheritance", "b) C++ technique to ensure that a private member of the base class can be accessed somehow", "c) C++ technique to avoid multiple inheritances of classes", "d) C++ technique to avoid multiple copies of the base class into children/derived class"},
        4
    };

    Question q10 = {
        "What happens if the following C++ statement is compiled and executed?\n\nint *ptr = NULL;\ndelete ptr;",
        {"a) The program is not semantically correct", "b) The program is compiled and executed successfully", "c) The program gives a compile-time error", "d) The program compiled successfully but throws an error during run-time"},
        2
    };

    questions.push_back(q1);
     questions.push_back(q2);
     questions.push_back(q3);
    questions.push_back(q4);
      questions.push_back(q5);
    questions.push_back(q6);
    questions.push_back(q7);
     questions.push_back(q8);
    questions.push_back(q9);
     questions.push_back(q10);
return questions;
}
list<Question> loadQuestionsForLevel2() {
    list<Question> questions; 
     Question q1 = {
        "What will be the output of the following C++ code?\n\n#include <iostream> \n#include <string>\nusing namespace std; \nint main(int argc, char const *argv[])\n{\n\tchar s1[6] = \"Hello\";\n\tchar s2[6] = \"World\";\n\tchar s3[12] = s1 + \" \" + s2;\n\tcout<<s3;\n\treturn 0;\n}",
        {"a) Hello", "b) World", "c) Error", "d) Hello World"},
        3
    };

    Question q2 = {
        "Which of the following C++ code will give an error on compilation?\n\n================code 1=================\n#include <iostream>\nusing namespace std;\nint main(int argc, char const *argv[])\n{\n\tcout<<\"Hello World\";\n\treturn 0;\n}\n========================================\n================code 2=================\n#include <iostream>\nint main(int argc, char const *argv[])\n{\n\tstd::cout<<\"Hello World\";\n\treturn 0;\n}\n========================================",
        {"a) Code 1 only", "b) Neither code 1 nor code 2", "c) Both code 1 and code 2", "d) Code 2 only"},
        2
    };

    Question q3 = {
        "What is the value of p in the following C++ code snippet?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint p;\n\tbool a = true;\n\tbool b = false;\n\tint x = 10;\n\tint y = 5;\n\tp = ((x | y) + (a + b));\n\tcout << p;\n\treturn 0;\n}",
        {"a) 12", "b) 0", "c) 2", "d) 16"},
        4
    };

    Question q4 = {
        "What will be the output of the following C++ function?\n\nint main()\n{\n\tregister int i = 1;\n\tint *ptr = &i;\n\tcout << *ptr;\n\treturn 0;\n}",
        {"a) Runtime error may be possible", "b) Compiler error may be possible", "c) 1", "d) 0"},
        2
    };

    Question q5 = {
        "What will be the output of the following C++ code?\n\n#include<iostream>\nusing namespace std;\nint main ()\n{\n   int cin;\n   cin >> cin;\n   cout << \"cin: \" << cin;\n   return 0;\n}",
        {"a) Segmentation fault", "b) Nothing is printed", "c) Error", "d) cin: garbage value"},
        4
    };

    Question q6 = {
        "What will be the output of the following C++ program?\n\n#include <iostream> \n#include <string>\n#include <cstring>\nusing namespace std; \nint main(int argc, char const *argv[])\n{\n\tconst char *a = \"Hello\\0World\";\n\tcout<<a;\n\treturn 0;\n}",
        {"a) Hello", "b) World", "c) Error", "d) Hello World"},
        1
    };

    Question q7 = {
        "What will be the output of the following C++ program?\n\n#include <iomanip>\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tcout << setprecision(17);\n\tdouble d = 0.1;\n\tcout << d << endl;\n\treturn 0;\n}",
        {"a) compile time error", "b) 0.100001", "c) 0.11", "d) 0.10000000000000001"},
        4
    };

    Question q8 = {
        "What will be the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint a = 5;\n\tfloat b;\n\tcout << sizeof(++a + b);\n\tcout << a;\n\treturn 0;\n}",
        {"a) 2 5", "b) 4 5", "c) 4 6", "d) 2 6"},
        2
    };

    Question q9 = {
        "What will be the output of the following C++ program?\n\n#include<iostream>\nusing namespace std;\nint main()\n{\n\tint a = 5;\n\tauto check = [=]() \n        {\n\t\ta = 10;\n\t};\n\tcheck();\n\tcout<<\"Value of a: \"<<a<<endl;\n\treturn 0;\n}",
        {"a) Segmentation fault", "b) Value of a: 5", "c) Value of a: 10", "d) Error"},
        4
    };

    Question q10 = {
        "What will be the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nvoid square (int *x, int *y)\n{\n\t*x = (*x) * --(*y);\n}\nint main ( )\n{\n\tint number = 30;\n\tsquare(&number, &number);\n\tcout << number;\n\treturn 0;\n}",
        {"a) 30", "b) Error", "c) Segmentation fault", "d) 870"},
        4
    };


    questions.push_back(q1);
    questions.push_back(q2);
    questions.push_back(q3);
    questions.push_back(q4);
    questions.push_back(q5);
    questions.push_back(q6);
    questions.push_back(q7);
    questions.push_back(q8);
    questions.push_back(q9);
    questions.push_back(q10);

    return questions;
}
  

list<Question> loadQuestionsForLevel3() {
    list<Question> questions; 
      Question q1 = {
        "What will be the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nvoid square (int *x, int *y)\n{\n\t*x = (*x) * --(*y);\n}\nint main ( )\n{\n\tint number = 30;\n\tsquare(&number, &number);\n\tcout << number;\n\treturn 0;\n}",
        {"a) 30", "b) Error", "c) Segmentation fault", "d) 870"},
        4
    };
    Question q2 = {
    "What will be the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint arr[] = {1, 2, 3, 4, 5};\n\tcout << *(arr + 2);\n\treturn 0;\n}",
    {"a) 2", "b) 3", "c) 4", "d) Error"},
    2
};
Question q3 = {
    "What is the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint x = 5;\n\tcout << x++ << ++x;\n\treturn 0;\n}",
    {"a) 56", "b) 66", "c) 57", "d) 65"},
    1
};
Question q4 = {
    "What will be the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nvoid swap(int &a, int &b)\n{\n\ta = a + b;\n\tb = a - b;\n\ta = a - b;\n}\nint main()\n{\n\tint x = 5, y = 10;\n\tswap(x, y);\n\tcout << x << ' ' << y;\n\treturn 0;\n}",
    {"a) 10 5", "b) 5 10", "c) 15 5", "d) 15 10"},
    1
};
Question q5 = {
    "What is the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint i = 5;\n\tcout << (++i) + (i++) + (++i);\n\treturn 0;\n}",
    {"a) 18", "b) 16", "c) 15", "d) 17"},
    4
};
Question q6 = {
    "What will be the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint a = 5, b = 2;\n\tcout << (a / b) * b + (a % b);\n\treturn 0;\n}",
    {"a) 5", "b) 2", "c) 7", "d) 1"},
    1
};
Question q7 = {
    "What is the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint num = 8;\n\tcout << (num >> 1) << ' ' << (num << 1);\n\treturn 0;\n}",
    {"a) 4 16", "b) 8 8", "c) 2 2", "d) 16 4"},
    1
};
Question q8 = {
    "What will be the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint x = 10;\n\tcout << (x & 1) << ' ' << (x | 1);\n\treturn 0;\n}",
    {"a) 0 11", "b) 1 10", "c) 1 11", "d) 0 10"},
    3
};
Question q9 = {
    "What is the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint arr[5] = {1, 2, 3, 4, 5};\n\tint *ptr = arr + 3;\n\tcout << *ptr;\n\treturn 0;\n}",
    {"a) 3", "b) 4", "c) 5", "d) 2"},
    2
};
Question q10 = {
    "What will be the output of the following C++ code?\n\n#include <iostream>\nusing namespace std;\nint main()\n{\n\tint n = 3;\n\tcout << n++ << ' ' << ++n << ' ' << n-- << ' ' << --n;\n\treturn 0;\n}",
    {"a) 3 5 5 3", "b) 4 5 4 3", "c) 3 4 4 3", "d) 3 4 5 3"},
    1
};

questions.push_back(q1);
questions.push_back(q2);
    questions.push_back(q3);
    questions.push_back(q4);
    questions.push_back(q5);
    questions.push_back(q6);
    questions.push_back(q7);
    questions.push_back(q8);
    questions.push_back(q9);
    questions.push_back(q10);
   
    return questions;
}
void playLevel(User& user, int level, int& score, int totalQuestions) {
    int levelScore = 0;
    list<Question> questions;
    if (level == 1) {
        questions = loadQuestionsForLevel1();
    } 
    else if (level == 2) {
        questions = loadQuestionsForLevel2();
    } 
    else if (level == 3) {
        questions = loadQuestionsForLevel3();
    }

stack<Question> questionStack;
    for (const auto& question : questions) {
        questionStack.push(question);
    }

    list<Question> incorrectQuestions;

    while (!questionStack.empty()) {
        system("clear"); 
        cout << "Level " << level << " - Question " << (questions.size() - questionStack.size() + 1) << endl;
        Question currentQuestion = questionStack.top();
        questionStack.pop();

        cout << currentQuestion.questionText << endl;

        for (const string& option : currentQuestion.options) {
            cout << option << endl;
        }

        int userChoice;
        cin >> userChoice;

        if (userChoice == currentQuestion.correctOption) {
            cout << "Well done! Correct option." << endl;
            levelScore++;
        } else {
            cout << "Wrong answer. Do you want to try this question again? (yes/no): ";
            string response;
            cin >> response;
            if (response == "yes") {
                questionStack.push(currentQuestion); 
            } 
            else {
                incorrectQuestions.push_back(currentQuestion);
                cout << "Correct answer: " << *next(currentQuestion.options.begin(), currentQuestion.correctOption - 1) << endl;
            }
        }

        cin.ignore(); 
    }

    system("clear");
    cout << "Level " << level << " completed." << endl;
    cout << "Score for Level " << level << ": " << levelScore << "/" << totalQuestions << endl;

    cout << "Press Enter to continue...";
    cin.ignore();

    if (!incorrectQuestions.empty()) {
        system("clear");
        cout << "Incorrect Questions for Level " << level << ":" << endl;
        for (const Question& question : incorrectQuestions) {
            cout << question.questionText << endl;
            cout << "Correct answer: " << *next(question.options.begin(), question.correctOption - 1) << endl;
            cout << endl;
        }
        cout << "Press Enter to continue...";
        cin.ignore();
    }

    score += levelScore;
   
}

void displayFinalScore(User user) {
    system("clear");
    cout << "Congratulations, " << user.name << "!" << endl;
    cout << "Your final score: " << user.score << "/30" << endl;

    string grade;
    if (user.score >= 25) {
        grade = "Excellent";
    } else if (user.score >= 20) {
        grade = "Good";
    } else if (user.score >= 15) {
        grade = "Average";
    } else {
        grade = "Needs improvement";
    }

    cout << "Overall grade: " << grade << endl;
    cout << "Thank you for playing ByteBuster Quiz!" << endl;
}

int main() {
    welcomePage();
    User user = getUserInfo();

    if (askToPlay(user)) {
        user.score = 0;

        for (int level = 1; level <= 3; level++) {
            int totalQuestions = (level == 1) ? 10 : (level == 2) ? 10 : 10; 
            playLevel(user, level, user.score, totalQuestions);
        }

        displayFinalScore(user);
    }

    return 0;
}
