# Python-Voting-System
#TAKE INPUT OF THE NOMINEES 
nominee1 = input("Enter the Name of 1st nominee:")
nominee2 = input("Enter the Name of 2nd nominee:")

#SET VOTE COUT INITIALLY AS 0 FOR BOTH
nominee1_votes = 0
nominee2_votes = 0

voter_id =[1,2,3,4,5,6,7,8,9,10] #VOTER LIST NUMBERS

no_of_voter = len(voter_id)  #LENGTH OF THE VOTER_ID

while True:
    if voter_id ==[]: # TO CHECK THE VOTER LIST IS EMPTY
        print("voting session is over")
        if nominee1_votes>nominee2_votes: #WHEN NOMINEE1 WONS VOTE GREATER THAN NOMINEE2
            percent=(nominee1_votes/no_of_voter)*100 #CALCULATE THE PERCENTAGE
            print(nominee1,"Has won the election",percent,"% of vote")
            break
        elif nominee2_votes>nominee1_votes: #WHEN NOMINEE2 WONS VOTE GREATER THAN NOMINEE1
            percent=(nominee2_votes/no_of_voter)*100#CALCULATE THE PERCENTAGE
            print(nominee2,"Has won the election",percent,"% of vote")
            break
        else:
            print("both have equal number of vote !!!!!")
            break

    voter = int(input("Enter your voter id:"))
    if voter in voter_id:
        print("You Are a voter")
        voter_id.remove(voter)  #REMOVE THE VOTER_ID SO NO VOTER CAN VOTE AGAIN
        print("---------------------------------")
        print("To Give Vote To",nominee1,"Press 1")
        print("To Give vote To",nominee2,"Press 2")
        print("-----------------------------------")
        vote = int(input("Enter your  Vote :"))
        if vote == 1:
            nominee1_votes +=1
            print(nominee1,"Thanks You to give your vote!!")
        elif vote == 2:
            nominee2_votes+=1
            print(nominee2,"Thanks You to give your vote!!")
        elif vote >2:
            print("check the pressed key")
        else:
            print("you are not a voter or alredy voted")
