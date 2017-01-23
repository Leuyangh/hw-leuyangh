#include <iostream>
#include <iomanip>
#include <string>
#include <fstream>
#include <cmath>
using namespace std;

// *You* are not allowed to use global variables
//  but for just the output portion *we* will. ;>
int combo = 1;

// @brief Prints a single combination of teams
//
// @param[in] team1 Array containing the names of team 1
// @param[in] team2 Array containing the names of team 2
// @param[in] len Size of each array
void printSolution(const string* team1, 
		   const string* team2,
		   int len)
{
  cout << "\nCombination " << combo++ << endl;
  cout << "T1: ";
  for(int i=0; i < len; i++){
    cout << team1[i] << " ";
  }
  cout << endl;
  cout << "T2: ";
  for(int i=0; i < len; i++){
    cout << team2[i] << " ";
  }
  cout << endl;
}


  string* generate_team2 (string* team1, string* names, int players);
  bool is_in(string player, string* team1, int players);
  void generate_team1(string* names, string* team1, int players,
    int position, int current){
      if (position == players/2){ //full team
         for (int i = 0; i < players/2; i++){
            for (int j = 0; j < players/2; j++){
               if(team1[i] == team1[j] && i != j){
                  return;
               }
               
            }
         }
         string* b = generate_team2(team1, names, players);
         printSolution(team1, b, players/2);
         return;
    }
    for(int i = current; i < players; i++){
      team1[position] = names[i];
      generate_team1(names, team1, players, position+1, i+1);
      
    }
  }
  int factorial(int n){
    if (n==1) return 1;
    else{
      return (n * factorial(n-1));
    }
  }
  
  bool is_in(string player, string* team1, int players){
    for (int i = 0; i < players/2; i++){
        if (team1[i] == player){
          return true;
        }
    }
    return false;
  }
  string* generate_team2 (string* team1, string* names, int players){
    string* team2 = new string[players/2];
    int team2member = 0;
    for (int i = 0; i < players; i++){
      if (!is_in(names[i], team1, players)){
        team2[team2member] = names[i];
        team2member++;
      }  
    }
    //cout << team2[0] << " " << team2[1] << endl;
    return team2;
  }



int main(int argc, char* argv[])
{
  if(argc < 2){
    cerr << "Please provide a file of names" << endl;
    return 1;
  }
  // Complete the rest of main
  ifstream ifile(argv[1]);
  if(ifile.fail()){
    cout << "Error" << endl;
    return 1;
  }
  int players;
  ifile >> players;
  string* names = new string[players];
  for (int i = 0; i < players; i++){
      ifile >> names[i];
      if(ifile.fail()){
        cout << "Error" << endl;
        return 1;
        }
  }
  string* team1 = new string[players/2];
  generate_team1(names, team1, players, 0, 0);
  return 0;
}
