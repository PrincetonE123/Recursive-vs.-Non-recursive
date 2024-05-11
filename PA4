/****************************************
PA-4-Source.cpp

Princeton Epeagba, J00701287
****************************************/

#include <chrono>
#include <iostream>
#include <vector>

using namespace std;
using namespace std::chrono;

void printWaysToReachTopUtillity(int totalSteps, vector<int> &leaps,
                                 vector<int> &path,
                                 vector<vector<int>> &result);
void printWaysToReachTop(int totalSteps, vector<int> &leaps);
int countWaysRecursive(int totalSteps, const vector<int> &leaps);
int countWaysNonRecursive(int totalSteps, const vector<int> &leaps);


int main() {
    int totalSteps;
    cout << "Enter the total number of steps: ";
    cin >> totalSteps;

    int numLeaps;
    cout << "Enter how many different leap values there are: ";
    cin >> numLeaps;

    vector<int> leaps(numLeaps);
    cout << "Enter the leap values one at a time: ";
    for (int i = 0; i < numLeaps; ++i) {
        cin >> leaps[i];
    }

    // Time for recursive algorithm
    auto startRecursive = high_resolution_clock::now();
    int recursiveWays = countWaysRecursive(totalSteps, leaps);
    auto stopRecursive = high_resolution_clock::now();
    auto durationRecursive = duration_cast<microseconds>(stopRecursive - startRecursive);

    // Time for non recursive algorithm
    auto startNonRecursive = high_resolution_clock::now();
  //  int nonRecursiveWays = countWaysNonRecursive(totalSteps, leaps);
    auto stopNonRecursive = high_resolution_clock::now();
    auto durationNonRecursive = duration_cast<microseconds>(stopNonRecursive - startNonRecursive);


    cout << "The time elapsed in the recursive algorithm is " << durationRecursive.count() << " microseconds." << endl;
    cout << "The time elapsed in the non-recursive algorithm is " << durationNonRecursive.count() << " microseconds." << endl;

    cout << "There are a total of " << recursiveWays << " ways." << endl;

    printWaysToReachTop(totalSteps, leaps);

    return 0;
}

// Helper function for recursive backtracking
void printWaysToReachTopUtillity(int totalSteps, vector<int> &leaps,
                                 vector<int> &path,
                                 vector<vector<int>> &result) {
  if (totalSteps == 0) {
    result.push_back(path);
    return;
  }

  for (int leap : leaps) {
    if (totalSteps - leap >= 0) {
      path.push_back(leap);
      printWaysToReachTopUtillity(totalSteps - leap, leaps, path, result);
      path.pop_back();
    }
  }
}

// Prints all the ways to reach the top of stairs
void printWaysToReachTop(int totalSteps, vector<int> &leaps) {
  vector<vector<int>> result; // creates 2D vector list for output
  vector<int> path;
  printWaysToReachTopUtillity(totalSteps, leaps, path, result);

  if (result.empty()) {
    cout << "No way possible" << endl;
  } else {
    cout << "Ways to reach the top:" << endl;
    int wayCount = 1;

    for (const vector<int> &way : result) {
      cout << "Way " << wayCount++ << ": ";

      for (int i = 0; i < way.size(); ++i) {
        cout << way[i];

        if (i < way.size() - 1) {
          cout << " -> ";
        }
      }

      cout << endl;
    }
  }
}

// Recursive algorithm
int countWaysRecursive(int totalSteps, const vector<int> &leaps) {
  if (totalSteps == 0) {
    return 1;
  }

  int rWays = 0;

  for (int leap : leaps) {
    if (totalSteps - leap >= 0) {
      rWays += countWaysRecursive(totalSteps - leap, leaps);
    }
  }

  return rWays;
}

// Non-recursive algorithm
int countWaysNonRecursive(int totalSteps, const vector<int> &leaps) {
  vector<int> nRways(totalSteps + 1, 0);
  nRways[0] = 1;

  for (int i = 1; i <= totalSteps; ++i) {
    for (int leap : leaps) {
      if (i - leap >= 0) {
        nRways[i] += nRways[i - leap];
      }
    }
  }

  return nRways[totalSteps];
}
