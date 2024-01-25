#include <fstream>
#include <iostream>
#include <locale>
#include <sstream>
#include <algorithm>
#include <string>
#include <vector>
#include <regex>
#include <iterator>
using namespace std;

int main(int argc, char *argv[])
{
    string filename = "test.txt";
    fstream myfile;
    myfile.open(filename);
    ///////////////////////////////WORD VECTOR//////////////////////////////////////
    vector<string> buffer;
    vector<string> words;
    vector<string> copyv;
    vector<string> wv;
    string intstring;
    string lower;
    string buffer2;
    string word;
    vector<string> holder;
    while (getline(myfile, intstring))
    {
        holder.push_back(intstring);
        stringstream hfinal(intstring);
        while (getline(hfinal, lower, '\n'))
        {
            stringstream wfinal(lower);
            while (getline(wfinal, buffer2, '.'))
            {

                char reader = buffer2.front();
                char space = ' ';
                if (reader == space)
                {
                    buffer2.erase(0, 1);
                }
                else
                    copyv.push_back(buffer2);
            }
        }
    }
    stringstream holding;
    copy(holder.begin(), holder.end(), ostream_iterator<string>(holding));
    string copystring;
    while (getline(holding, copystring, ' '))
    {

        words.push_back(copystring);
    }

    for (int i = 0; i < words.size(); i++)
    {
        for (auto &ch : words[i])
        {
            ch = tolower(ch, locale());
        }
    }
    ///////////////////////finding max word///////////////////////////////

    ////////////////making copies
    vector<string> cwords;
    for (int i = 0; i < words.size(); i++)
    {
        cwords.push_back(words[i]);
    }
    sort(cwords.begin(), cwords.end());
    auto uni = unique(cwords.begin(), cwords.end());
    cwords.resize(distance(cwords.begin(), uni));

    string test;
    vector<string> unicopy;
    for (uni = cwords.begin(); uni != cwords.end(); uni++)
    {
        // copy << *uni;
        stringstream copy1(*uni);
        getline(copy1, test, '.');
        unicopy.push_back(test);
        /// COPY IS THE VECTOR TO USE WHILE COMPARING THE OG
    }
    ////////counting all words
    int sizeofOG = words.size();
    int sizeofcopy = unicopy.size();
    vector<int> countofwordsOG;
    vector<int> unicountofwords;

    stringstream finalcounter;

    int reapcount = 1;
    for (int i = 0; i <= sizeofcopy; i++)
    {
        for (int x = 0; x <= sizeofOG; x++)
        {
            if (unicopy[i] == words[x])
            {
                reapcount++;
            }
        }
        countofwordsOG.push_back(reapcount);

        finalcounter << unicopy[i] << ":" << countofwordsOG[i] << endl;
        reapcount = 1;
    }
    ///////find most counted word
    vector<string> copyofss;
    string vector1;
    vector<char> charA;
    while (getline(finalcounter, vector1, '\n'))
    {
        copyofss.push_back(vector1);
    }
    sort(countofwordsOG.begin(), countofwordsOG.end(), greater<int>());
    sort(copyofss.begin(), copyofss.end(), greater<string>());
    int &max = countofwordsOG[0];
    ostringstream ss;
    string smax;
    ss << max;
    smax = ss.str();

    for (int i = 0; i < countofwordsOG.size(); i++)
    {
        regex r(smax);
        string scap = copyofss[i];
        if (regex_search(scap, r))
        {
            cout << copyofss[i] << endl;
        }
    }
    // basically just keep deleting the next max till you get to the third one fuck it
    vector<int> copyofOG;
    for (int i = 0; i < countofwordsOG.size(); i++)
    {
        copyofOG.push_back(countofwordsOG[i]);
    }
    sort(copyofOG.begin(), copyofOG.end(), greater<int>());
    copyofOG.erase(copyofOG.begin());
    copyofOG.erase(copyofOG.begin());
    sort(copyofOG.begin(), copyofOG.end(), greater<int>());
    int maxof3 = copyofOG[0];
    ostringstream st;
    string smax3;
    st << maxof3;
    smax3 = st.str();
    for (int i = 0; i < countofwordsOG.size(); i++)
    {
        regex r(smax3);
        string scap = copyofss[i];
        if (regex_search(scap, r))
        {
            cout << copyofss[i] << endl;
        }
    }
    //////////////////////////////////////THREE-NINE/////////////////////////////////
    vector<string> tempcopy;
    string intstring2;
    string lower2;

    ////////////sentence vector////////////////

    for (int i = 0; i < copyv.size(); i++)
    {
        for (auto &ch : copyv[i])
        {
            ch = tolower(ch, locale());
        }
    }
    /*for(int i=0; i<copyv.size();i++)
    {
        for(int x=0;x<words.size();x++)
        {
            if(words[i]==" ")
            {
                auto it=copyv.begin();
                words.erase(it);
            }
        }
    }*/
    ////////////word vector////////////
    for (int i = 0; i < copyv.size(); i++)
    {

        wv.push_back(copyv[i]);
    }
    stringstream sstoken;
    string token;
    vector<string> wvword;
    for (auto i = wv.begin(); i != wv.end(); i++)
    {
        if (i != wv.begin())
        {
            sstoken << " ";
        }
        sstoken << *i;
    }
    while (getline(sstoken, token, ' '))
    {
        wvword.push_back(token);
    }
    /*
    /////////////////FINDING 3////////////////////////
    vector<string> sortedsens;
    vector<int> wordcounts;
    int counter = 1;

    for (int i = 0; i < copyv.size(); i++)
    {
        stringstream ss(copyv[i]);
        string cap;
        vector<string> word;

        while (getline(ss, cap, ' '))
        {
            word.push_back(cap);
        }
        for (int x = 0; x < word.size(); x++)
        {

            if (word[x] == word[x + 1])
            {

                counter++;
            }
        }

        wordcounts.push_back(counter);
        cout << counter << ":" <<copyv[i] << endl;
        counter = 1;
    }

   */

    /////////////////FIND 4-9//////////////////
    ////////////////////sentence vector with "%" instead of space////////////////

    vector<string> spacechange;
    for (int i = 0; i < copyv.size(); i++)
    {
        spacechange.push_back(copyv[i]);
    }
    vector<string> spacechange2;
    vector<string> spacechange3;
    vector<string> spacechange4;
    vector<string> spacechange5;
    vector<string> spacechange6;
    vector<string> spacechange7;
    vector<string> spacechange8;
    vector<string> spacechange9;
    vector<string> spacechange10;
    vector<string> spacechange11;
    vector<string> spacechange12;
    vector<string> spacechange13;
    vector<string> spacechange14;
    vector<string> spacechange15;

    for (int i = 0; i < spacechange.size(); i++)
    {
        spacechange2.push_back(regex_replace(spacechange[i], regex("there"), "thre"));
        spacechange3.push_back(spacechange2[i]);
    }
    for (int i = 0; i < spacechange.size(); i++)
    {
        spacechange4.push_back(regex_replace(spacechange3[i], regex("it was"), "it%was"));
        spacechange5.push_back(spacechange4[i]);
    }
    for (int i = 0; i < spacechange.size(); i++)
    {
        spacechange6.push_back(regex_replace(spacechange5[i], regex("but the"), "but%the"));
        spacechange7.push_back(spacechange6[i]);
    }
    for (int i = 0; i < spacechange.size(); i++)
    {
        spacechange8.push_back(regex_replace(spacechange7[i], regex("in my"), "in%my"));
        spacechange9.push_back(spacechange8[i]);
    }
    for (int i = 0; i < spacechange.size(); i++)
    {
        spacechange10.push_back(regex_replace(spacechange9[i], regex("was"), "was "));
        spacechange11.push_back(spacechange10[i]);
    }
    for (int i = 0; i < spacechange.size(); i++)
    {
        spacechange12.push_back(regex_replace(spacechange11[i], regex("of"), "of "));
        spacechange13.push_back(spacechange12[i]);
    }
    for (int i = 0; i < spacechange.size(); i++)
    {
        spacechange14.push_back(regex_replace(spacechange13[i], regex("the"), "the "));
        spacechange15.push_back(spacechange14[i]);
    }
    // for (int i = 0; i < spacechange.size(); i++)
    // {

    //  cout << spacechange2[i] << endl;
    //}
    vector<int> maxholder;
    vector<string> copyofWNS;
    vector<string> search = {"the", "of", "was", "but%the", "it%was", "in%my"};
    vector<string> printer = {"the", "of", "was", "but the", "it was", "in my"};
    ////////////////IT WILL PRINT AN INSTANCE (THE, "THERE")///////////////////////////////
    for (int jeff = 0; jeff < search.size(); jeff++)
    {
        string the = search[jeff];
        int repcount = 0;
        smatch m;
        regex rasp(search[jeff]);
        vector<int> highcount;
        stringstream wordnumsentence;
        for (int i = 0; i < copyv.size(); i++)
        {
            stringstream ss(spacechange15[i]);
            string cap;
            vector<string> word;

            while (getline(ss, cap, ' '))
            {
                word.push_back(cap);
            }
            for (int x = 0; x < word.size(); x++)
            {

                if (regex_search(word[x], m, rasp)) // issue is here, youre comparing one word at a time.
                {

                    repcount++;
                }
            }

            highcount.push_back(repcount);
            wordnumsentence << printer[jeff] << ":" << repcount << ":" << copyv[i] << endl;
            repcount = 0;
        }

        string WNShold;
        while (getline(wordnumsentence, WNShold, '\n'))
        {
            copyofWNS.push_back(WNShold);
        }

        sort(copyofWNS.begin(), copyofWNS.end(), greater<string>());
        sort(highcount.begin(), highcount.end(), greater<int>());
        int maxofword = highcount[0];
        ostringstream max;
        string damax;
        max << maxofword;
        damax = max.str();
        maxholder.push_back(maxofword);

       /* for (int ger = 0; ger < 4; ger++)
        {
            ofstream outfile;
            ostringstream filer;
            outfile.open(argv[2]);
            string thefile = filer.str();
            outfile.open(thefile, ios::app);
            regex r(damax);
            string alphacap = copyofWNS[ger];
            if (regex_search(alphacap, r))
            {
                outfile << copyofWNS[ger] << endl; /// OUTPUTFILES EVENTUALLY GO HERE
            }
            outfile.close();
        }*/
    }
    sort(maxholder.begin(), maxholder.end(), greater<int>());
    ////////////////the
    for (int i = 0; i < copyofWNS.size(); i++)
    {

        ofstream outfile;
        ostringstream filer;
        string ofile = "output";
        filer << argv[2] << "4"
              << ".txt";
        string thefile = filer.str();
        outfile.open(thefile);
        string str = copyofWNS[i];
        stringstream ss;
        ss << "the:" << maxholder[0] << ":";
        string holder = ss.str();
        std::size_t found = str.find(holder);
        if ((found != string::npos))
        {
            outfile << copyofWNS[i];
        }
      outfile.close();
    }

    /////////////////of
    for (int i = 0; i < copyofWNS.size(); i++)
    {
        ofstream outfile;
        ostringstream filer;
        string ofile = "output";
        filer << argv[2] << "5"
              << ".txt";
        string thefile = filer.str();
        outfile.open(thefile);
        string str = copyofWNS[i];
        stringstream ss;
        ss << "of:" << maxholder[1] << ":";
        string holder = ss.str();
        std::size_t found = str.find(holder);
        if ((found != string::npos))
        {
            outfile << copyofWNS[i];
        }
      outfile.close();
    }

    /////////////////was
    for (int i = 0; i < copyofWNS.size(); i++)
    {
        ofstream outfile;
        ostringstream filer;
        string ofile = "output";
        filer << argv[2] << "6"
              << ".txt";
        string thefile = filer.str();
        outfile.open(thefile);
        string str = copyofWNS[i];
        stringstream ss;
        ss << "was:" << maxholder[2] << ":";
        string holder = ss.str();
        std::size_t found = str.find(holder);
        if ((found != string::npos))
        {
            outfile << copyofWNS[i];
        }
      outfile.close();
    }

    //////////////////////////but the
    for (int i = 0; i < copyofWNS.size(); i++)
    {
        ofstream outfile;
        ostringstream filer;
        string ofile = "output";
        filer << argv[2] << "7"
              << ".txt";
        string thefile = filer.str();
        outfile.open(thefile);

        string str = copyofWNS[i];
        stringstream ss;
        ss << "but the:" << maxholder[3] << ":";
        string holder = ss.str();
        std::size_t found = str.find(holder);
        if ((found != string::npos))
        {
            outfile << copyofWNS[i];
        }
      outfile.close();
    }

    ///////////////////////it was
    for (int i = 0; i < copyofWNS.size(); i++)
    {
        ofstream outfile;
        ostringstream filer;
        string ofile = "output";
        filer << argv[2] << "8"
              << ".txt";
        string thefile = filer.str();
        outfile.open(thefile);
        string str = copyofWNS[i];
        stringstream ss;
        ss << "it was:" << maxholder[4] << ":";
        string holder = ss.str();
        std::size_t found = str.find(holder);
        if ((found != string::npos))
        {
            outfile << copyofWNS[i];
        }
      outfile.close();
    }
    /////////////////////in my
    for (int i = 0; i < copyofWNS.size(); i++)
    {
        ofstream outfile;
        ostringstream filer;
        string ofile = "output";
        filer << argv[2] << "9"
              << ".txt";
        string thefile = filer.str();
        outfile.open(thefile);

        string str = copyofWNS[i];
        stringstream ss;
        ss << "in my:" << maxholder[5] << ":";
        string holder = ss.str();
        std::size_t found = str.find(holder);
        if ((found != string::npos))
        {
           outfile << copyofWNS[i];
        }
      outfile.close();
    }
}
