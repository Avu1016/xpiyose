1.2. The source code management life cycle for collaborative software development which involves stages such as :

- Planning: This stage involves defining the scope of the project, setting objectives, and determining the tasks needed to achieve those objectives. During this stage, developers can create a roadmap, define features as well as allocate resources.

- Development: In this stage, developers write the code based on the requirements outlined in the planning stage,which includes coding, testing, and debugging codes as well as collaborative tools like Git are used to manage changes, track progress, and facilitate collaboration between team members.

- Testing: Once the code is developed, it needs to be thoroughly tested to ensure that it functions correctly and meets the specified requirements. This stage involves various types of testing, such as unit testing, integration testing, and acceptance testing.

- Deployment: Once the code passes testing, it is ready to be deployed to the production environment. This stage involves preparing the code for deployment, configuring servers, and deploying the application to end-users.

- Maintenance: Even after deployment, software requires ongoing maintenance to fix bugs, implement updates, and address user feedback. This stage involves monitoring the performance of the application, identifying and resolving issues, and making improvements as needed.

The Git commands used for each :

- Planning : 

git init my_project
cd my_project
touch README.md
git add README.md
git commit -m "Initial commit: Added README.md"

- Development :

git add

git commit -m "Added feature X and fixed bug i"

- Testing : 

git checkout -b feature_x_testing

git add

git commit -m "Tested feature X"

- Development :

git push origin main:staging



- Maintenance : 

git checkout -b fix_critical_bug

git add .

git commit -m "Fixed critical bug reported by users"

git checkout main
git merge fix_critical_bug

1.3.cd path/to/local machine/directory
git init

1.4. git checkout -b feature-voter-registration
echo "print('Register to vote, your vote is your power to make a change')" > registration.py
git add registration.py
git commit -m "Add registration message"
git checkout main
git merge feature-voter-registration

2.1. def register_party(parties):

    valid_parties = []
    invalid_parties = []

    for party in parties:
        party_name = party.get('party_name')
        reg_number = party.get('reg_number')
        member_count = party.get('member_count')

        if member_count >= 100:
            valid_parties.append(party)
        else:
            invalid_parties.append(party)

    return valid_parties, invalid_parties

2.2. 
def generate_next_reg_number(last_reg_number):
    return str(int(last_reg_number) + 1)

mk_party = {
    "party_name": "MK Party",
    "reg_number": generate_next_reg_number("10003318"),  
    "member_count": 5300
}


parties = [
    {"party_name": "Party A", "reg_number": "10003319", "member_count": 150},
    {"party_name": "Party B", "reg_number": "10003320", "member_count": 80},
    {"party_name": "Party C", "reg_number": "10003321", "member_count": 200},
]


valid_parties, invalid_parties = register_party(parties + [mk_party])


if mk_party in valid_parties:
    print("MK Party has been successfully registered.")
else:
    print("MK Party does not meet the registration criteria.")
2.3. git checkout -b update-voter-info

git checkout -b update-voter-info


mkdir voter_management
cd voter_management

touch voter_info.py



def update_voter_info(voter_info, voter_id, name, voting_district, has_voted):
    """
    Update voter's information or add a vote if not already voted.

    Args:
    - voter_info (dict): Dictionary containing voter information.
    - voter_id (str): Voter's ID.
    - name (str): Voter's name.
    - voting_district (str): Voter's voting district.
    - has_voted (bool): Indicates whether the voter has already voted.

    Returns:
    - voter_info (dict): Updated voter information dictionary.
    """
    if voter_id in voter_info:
        
        voter_info[voter_id]["name"] = name
        voter_info[voter_id]["voting_district"] = voting_district
        if not voter_info[voter_id]["has_voted"] and has_voted:
          
            voter_info[voter_id]["has_voted"] = has_voted
            print(f"Vote recorded for voter {voter_id}.")
        else:
            print(f"Voter {voter_id} has already voted.")
    else:
        
        voter_info[voter_id] = {
            "name": name,
            "voting_district": voting_district,
            "has_voted": has_voted
        }
        print(f"New voter {voter_id} added.")

    return voter_info

2.4. 
party_abbreviations = ["ANC", "DA", "EFF", "IFP", "BLF", "COPE", "UDM", "ACDP", "FF+", "GOOD", "NFP", "ATM", "PA", "PAC", "AIC", "AL JAMA-AH", "C4C", "ACM", "COPE-RENEWAL", "AFRICAN ALLIANCE OF SOCIAL DEMOCRACY", "ATM-WC", "ATM-NC", "UDM-EC", "UDM-NW", "UDM-FS", "UDM-GT", "UDM-KZN", "UDM-LP", "UDM-MP", "UDM-NC", "UDM-NW", "UDM-WC", "INDEPENDENT COUNCILLORS", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND", "IND"]

# Filter out parties with less than 1,000 members
filtered_parties = list(filter(lambda party: len(party) >= 1000, party_abbreviations))

print(filtered_parties)

2.5. 
party_abbreviations = [
    "ANC", "ASC", "ATM", "AASD", "AGANG SA" , "ALJAMA", "ATA" , "AZAPO", "APC" , "BRA" , "BLF" , "ZACP" , "CPM" , "CSA" , "COPE" ,"DA" , "DLC" , "ECOFORUM" , "EFF" , "F4SD" , "FREE DEMS"
]


filtered_parties = [party for party in party_abbreviations if len(party) >= 1000]

print(filtered_parties)

2.6.
voter_records = [
    {'id': 1, 'name': 'Avumile', 'registered': True},
    {'id': 2, 'name': 'Sanele', 'registered': False},
    {'id': 3, 'name': 'Sphesihle', 'registered': True},
    {'id': 4, 'name': 'Mpumelelo', 'registered': False},
    {'id': 5, 'name': 'Wendy', 'registered': True}
]

registered_voters = list(filter(lambda voter: voter['registered'], voter_records))

print(registered_voters)

3.1. import pandas as pd

football = pd.read_csv("football.csv")

print(football.head())

3.2. import pandas as pd

football = pd.read_csv("football.csv")

print(football.tail(7))

3.3.1. football = pd.read_csv("football.csv")
3.3.2. print(football.iloc[9])
3.3.3. print(football.loc[100:110, ["Goals", "Appearances"]])
3.3.4. football["Goals per Appearance"] = football["Goals"] / football["Appearances"]
print(football.head())
3.3.5. arsenal_players = football[football["Club"] == "Arsenal"]
print(arsenal_players)
3.3.6. high_scorers = football[football["Goals"] > 5]
print(high_scorers)

3.4. pip install --upgrade pandas
