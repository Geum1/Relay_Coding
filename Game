#include <iostream>
#include <string>
#include <vector>
#include <random>
#include <cstdlib>

using namespace std;

const int MAX_ITEM_SLOTS = 6;

class game;

class ChampionStats {			//기본스탯
	string name;
	vector<string> items;
	int experience,				//경험치
		range,					//사거리
		movementSpeed,			//이동 속도
		attackDamage,			//공격력
		abilityPower,			//주문력
		criticalStrikeChance,	//치명타 확률
		armor,					//방어력
		magicResistance,		//마법 저항력
		abilityhaste,			//스킬 가속
		armorPenetration,		//물리 관통력
		magicPenetration,		//마법 관통력
		lifesteal,				//생명력 흡수
		physicalvamp,			//물리 피해 흡혈
		omnivamp,				//모든 피해 흡혈
		healandShieldPower,		//회복 및 보호막 효과
		tenacity;				//강인함
	double attackSpeed,			//공격 속도
		health = 1,				//체력
		mana;					//마나
public:
	void setName(const string& value) { name = value; } // 이름 설정
	string getName() const { return name; }				// 이름 반환
	ChampionStats() {
		experience = 0;
		range = 0;
		movementSpeed = 0;
		attackDamage = 0;
		abilityPower = 0;
		criticalStrikeChance = 0;
		attackSpeed = 0;
		health = 0;
		mana = 0;
		armor = 0;
		magicResistance = 0;
		abilityhaste = 0;
		armorPenetration = 0;
		magicPenetration = 0;
		lifesteal = 0;
		physicalvamp = 0;
		omnivamp = 0;
		healandShieldPower = 0;
		tenacity = 0;
	}
	void setExperience(int value) { experience = value; }
	int getExperience() { return experience; }

	void setRange(int value) { range = value; }
	int getRange() { return range; }

	void setMovementSpeed(int value) { movementSpeed = value; }
	int getMovementSpeed() { return movementSpeed; }

	void setAttackDamage(int value) { attackDamage = value; }
	int getAttackDamage() { return attackDamage; }

	void setAbilityPower(int value) { abilityPower = value; }
	int getAbilityPower() { return abilityPower; }

	void setCriticalStrikeChance(int value) { criticalStrikeChance = value; }
	int getCriticalStrikeChance() { return criticalStrikeChance; }

	void setAttackSpeed(double value) { attackSpeed = value; }
	double getAttackSpeed() { return attackSpeed; }

	void setHealth(double value) { health = value; }
	double getHealth() { return health; }

	void setMana(double value) { mana = value; }
	double getMana() { return mana; }

	void setArmor(int value) { armor = value; }
	int getArmor() { return armor; }

	void setMagicResistance(int value) { magicResistance = value; }
	int getMagicResistance() { return magicResistance; }

	void setAbilityhaste(int value) { abilityhaste = value; }
	int getAbilityhaste() { return abilityhaste; }

	void setArmorPenetration(int value) { armorPenetration = value; }
	int getArmorPenetration() { return armorPenetration; }

	void setMagicPenetration(int value) { magicPenetration = value; }
	int getMagicPenetration() { return magicPenetration; }

	void setLifesteal(int value) { lifesteal = value; }
	int getLifesteal() { return lifesteal; }

	void setPhysicalvamp(int value) { physicalvamp = value; }
	int getPhysicalvamp() { return physicalvamp; }

	void setOmnivamp(int value) { omnivamp = value; }
	int getOmnivamp() { return omnivamp; }

	void setHealandShieldPower(int value) { healandShieldPower = value; }
	int getHealandShieldPower() { return healandShieldPower; }

	void setTenacity(int value) { tenacity = value; }
	int getTenacity() { return tenacity; }

	void setItems(string itme) { items.push_back(itme); }
	int getItems() { return items.size(); }
	void printItems() {
		cout << "Items: ";
		for (const string& item : items) {
			cout << item << ", ";
		}
		cout << endl;
	}
};

/* monster 클래스
여기에서 작성한 후
Class 이름
changeMonster(이름) 으로 업데이트 해주심 됨다...) */

class Slime : public ChampionStats {
public:
	Slime() {
		setName("슬라임"); // 이름 설정
		setExperience(0);
		setRange(50);
		setMovementSpeed(200);
		setAttackDamage(20);
		setAbilityPower(0);
		setCriticalStrikeChance(5);
		setAttackSpeed(1.0);
		setHealth(1000); // 체력을 1000으로 변경
		setMana(0);
		setArmor(10);
		setMagicResistance(5);
		setAbilityhaste(0);
		setArmorPenetration(0);
		setMagicPenetration(0);
		setLifesteal(0);
		setPhysicalvamp(0);
		setOmnivamp(0);
		setHealandShieldPower(0);
		setTenacity(0);
	};
};

class WarriorMinion : public ChampionStats {
public:
	WarriorMinion() {
		setName("전사 미니언"); // 이름 설정
		setExperience(0);
		setRange(110);
		setMovementSpeed(325);
		setAttackDamage(12);
		setAbilityPower(0);
		setCriticalStrikeChance(0);
		setAttackSpeed(1.25);
		setHealth(477); // 체력을 1000으로 변경
		setMana(0);
		setArmor(0);
		setMagicResistance(0);
		setAbilityhaste(0);
		setArmorPenetration(0);
		setMagicPenetration(0);
		setLifesteal(0);
		setPhysicalvamp(0);
		setOmnivamp(0);
		setHealandShieldPower(0);
		setTenacity(0);
	}
};

// game 클래스 선언부

class game : public ChampionStats {
	string playerName;
	ChampionStats* player, * monster, * warriorMinion;
	int gmaLevel = 0;
	bool gameRunning = true;
	Slime slime;
	WarriorMinion warriorminion;
public:
	void changeMonster(ChampionStats newMonsterStats) {
		monster = new ChampionStats(newMonsterStats); // fight 함수에서 monster에 대입할 업데이트 함수이다!!!!!! (ㅅㅂ 뭔말이야)
	}
	game() {
		player = new ChampionStats();
		monster = new ChampionStats();
	}
	game(int experience, int range, int movementSpeed, int attackDamage, int abilityPower, int criticalStrikeChance,
		double attackSpeed, double health, double mana, int armor, int magicResistance, int abilityhaste,
		int armorPenetration, int magicPenetration, int lifesteal, int physicalvamp, int omnivamp,
		int healandShieldPower, int tenacity)
	{
		setExperience(experience);
		setRange(range);
		setMovementSpeed(movementSpeed);
		setAttackDamage(attackDamage);
		setAbilityPower(abilityPower);
		setCriticalStrikeChance(criticalStrikeChance);
		setAttackSpeed(attackSpeed);
		setHealth(health);
		setMana(mana);
		setArmor(armor);
		setMagicResistance(magicResistance);
		setAbilityhaste(abilityhaste);
		setArmorPenetration(armorPenetration);
		setMagicPenetration(magicPenetration);
		setLifesteal(lifesteal);
		setPhysicalvamp(physicalvamp);
		setOmnivamp(omnivamp);
		setHealandShieldPower(healandShieldPower);
		setTenacity(tenacity);
	}
	void setPlayerName(string playerName) { this->playerName = playerName; }
	string getPlayerName() { return playerName; }
	void virtual run();
	void nowStatus(); // 현재 플레이어 상태;  
	void virtual fight();
	void tutorials();
	void virtual gmaeLevel() { gmaLevel++; };
	void getItem();
	bool run_away() {
		int run_awayran = rand() % 2;
		if (run_awayran == 1) {
			cout << getPlayerName() << "님이 성공적으로 도망쳤습니다!" << endl; return true;
		}
		else {
			cout << getPlayerName() << "님이 도망치려다 실패했습니다!" << endl; return false;
		}
	}
};
// 아이템 습득 ,아이템 스탯,아이템 슬롯 크기
void game::getItem() {
	const string items[15] = { "영겁의 지팡이", "대천사의 포옹", "존야의 모래시계",
										   "얼어붙은 심장", "라바돈의 죽음모자","우주의 추진력",
										   "공허의 지팡이", "몰락한 왕의 검", "구인수의 격노검",
										   "크라켄 학살자","마법사의 최후", "죽음의 무도",
										   "삼위일체", "루난의 허리케인", "유령 무희" };
	int randomIndex = rand() % 15; string item = items[randomIndex];
	player->setItems(item); cout << "플레이어가 " << item << " 아이템을 획득했습니다!" << endl << endl;

	if (player->getItems() > MAX_ITEM_SLOTS - 1) {
		cout << "슬롯이 모두 찼으므로 아이템을 더 이상 획득할 수 없습니다." << endl; return;
	}
	else {
	if (item == "영겁의 지팡이") {
		player->setAbilityPower(player->getAbilityPower() + 60);
		player->setHealth(player->getHealth() + 400);
		player->setMana(player->getMana() + 400);
	}
	else if (item == "대천사의 포옹") {
		player->setAbilityPower(player->getAbilityPower() + 70);
		player->setMana(player->getMana() + 860);
		player->setHealth(player->getHealth() + 200);
		player->setAbilityhaste(player->getAbilityhaste() + 10);
	}
	else if (item == "존야의 모래시계") {
		player->setAbilityPower(player->getAbilityPower() + 80);
		player->setArmor(player->getArmor() + 45);
		player->setAbilityhaste(player->getAbilityhaste() + 15);
	}
	else if (item == "얼어붙은 심장") {
		player->setArmor(player->getArmor() + 90);
		player->setMana(player->getMana() + 400);
		player->setAbilityhaste(player->getAbilityhaste() + 20);
	}
	else if (item == "라바돈의 죽음모자") {
		player->setAbilityPower(player->getAbilityPower() + 120);
	}
	else if (item == "우주의 추진력") {
		player->setAbilityPower(player->getAbilityPower() + 100);
		player->setAbilityhaste(player->getAbilityhaste() + 30);
		player->setMovementSpeed(player->getMovementSpeed() + 5);
	}
	else if (item == "공허의 지팡이") {
		player->setAbilityPower(player->getAbilityPower() + 65);
		player->setMagicPenetration(player->getMagicPenetration() + 40);
	}
	else if (item == "몰락한 왕의 검") {
		player->setAttackDamage(player->getAttackDamage() + 40);
		player->setAttackSpeed(player->getAttackSpeed() + 0.40);
		player->setLifesteal(player->getLifesteal() + 8);
	}
	else if (item == "구인수의 격노검") {
		player->setAttackDamage(player->getAttackDamage() + 30);
		player->setAbilityPower(player->getAbilityPower() + 30);
		player->setAttackSpeed(player->getAttackSpeed() + 0.25);
	}
	else if (item == "크라켄 학살자") {
		player->setAttackDamage(player->getAttackDamage() + 40);
		player->setAttackSpeed(player->getAttackSpeed() + 0.30);
		player->setCriticalStrikeChance(player->getCriticalStrikeChance() + 20);
	}
	else if (item == "마법사의 최후") {
		player->setAttackDamage(player->getAttackDamage() + 40);
		player->setAttackSpeed(player->getAttackSpeed() + 0.40);
		player->setMagicResistance(player->getMagicResistance() + 40);
	}
	else if (item == "죽음의 무도") {
		player->setAttackDamage(player->getAttackDamage() + 55);
		player->setAbilityhaste(player->getAbilityhaste() + 15);
		player->setArmor(player->getArmor() + 45);
	}
	else if (item == "삼위일체") {
		player->setAttackDamage(player->getAttackDamage() + 40);
		player->setAttackSpeed(player->getAttackSpeed() + 0.33);
		player->setHealth(player->getHealth() + 300);
		player->setAbilityhaste(player->getAbilityhaste() + 20);
	}
	else if (item == "루난의 허리케인") {
		player->setAttackSpeed(player->getAttackSpeed() + 1);
		player->setCriticalStrikeChance(player->getCriticalStrikeChance() + 1);
		player->setMovementSpeed(player->getMovementSpeed() + 1);
	}
	else if (item == "유령 무희") {
		player->setAttackDamage(player->getAttackDamage() + 20);
		player->setAttackSpeed(player->getAttackSpeed() + 1);
		player->setCriticalStrikeChance(player->getCriticalStrikeChance() + 1);
		player->setMovementSpeed(player->getMovementSpeed() + 1);
	}
	}
}
// 여기서 부터가 game 클래스 구현부 

void game::nowStatus()
{
	cout << "****현재 플레이어의 능력치 입니다.****" << endl << endl;
	cout << "[경험치 " << player->getExperience() << "]" << endl;
	cout << "[사거리 " << player->getRange() << "]" << endl;
	cout << "[이동 속도 " << player->getMovementSpeed() << "]" << endl;
	cout << "[공격력 " << player->getAttackDamage() << "]" << " [주문력 " << player->getAbilityPower() << "]" << endl;
	cout << "[치명타 확률 " << player->getCriticalStrikeChance() << "]" << " [공격 속도 " << player->getAttackSpeed() << "]" << endl;
	cout << "[체력 " << player->getHealth() << "]" << " [마나 " << player->getMana() << "]" << endl;
	cout << "[방어력 " << player->getArmor() << "]" << " [마법 저항력 " << player->getMagicResistance() << "]" << endl;
	cout << "[스킬 가속 " << player->getAbilityhaste() << "]" << endl;
	cout << "[물리 관통력 " << player->getArmorPenetration() << "]" << " [마법 관통력 " << player->getMagicPenetration() << "]" << endl;
	cout << "[생명력 흡수 " << player->getLifesteal() << "]" << " [물리 피해 흡혈 " << player->getPhysicalvamp() << "]" << endl;
	cout << "[모든 피해 흡혈 " << player->getOmnivamp() << "]" << endl;
	cout << "[회복 및 보호막 효과 " << player->getHealandShieldPower() << "]" << " [강인함 " << player->getTenacity() << "]" << endl << endl;
	cout << "**************************************" << endl << endl;
}

void game::fight()
{
	if (player->getHealth() <= 0) {
		gameRunning = false;
		cout << "사망하고 말았다." << endl;
		return;
	}

	if(rand()%2 == 0)
		changeMonster(slime);
	else
		changeMonster(warriorminion);

	while (player->getHealth() > 0 && monster->getHealth() > 0) {
		cout << "무엇을 할까요?" << endl << endl;
		cout << "[1 일반 공격] [2 스킬을 확인한다] [3 아이템을 확인한다] [4 도망간다]" << endl << endl;

		int playerChoice;
		cout << "-> "; cin >> playerChoice;
		cout << endl;

		switch (playerChoice)
		{
		case 1:
			// 플레이어의 일반 공격
			cout << getPlayerName() << "님이 일반 공격을 시전합니다!" << endl;
			monster->setHealth(monster->getHealth() - player->getAttackDamage());
			cout << monster->getName() << "에게 " << player->getAttackDamage() << "의 피해를 입혔습니다!" << endl << endl;
			break;
		case 2:
			// 스킬 사용 추가
			cout << getPlayerName() << "님이 스킬을 사용합니다!" << endl;
			// 스킬 사용에 대한 코드를 추가해주세요.
			break;
		case 3:
			// 아이템 확인 추가
			player->printItems();
			break;
		case 4:
			// 도망치기 추가
			if (run_away()) {
				cout << getPlayerName() << "님이 도망칩니다!" << endl; return;
			}
			break;
		default:
			cout << "잘못된 입력입니다. 다시 선택해주세요." << endl;
			break;
		}

		if (monster->getHealth() > 0) {
			// 몬스터의 공격
			cout << monster->getName() << "님이 공격합니다!" << endl;
			player->setHealth(player->getHealth() - monster->getAttackDamage());
			cout << getPlayerName() << "님이 " << monster->getAttackDamage() << "의 피해를 입었습니다!"  << endl;
		}

		// 턴이 끝난 후 상태 출력
		cout << endl;
		cout << getPlayerName() << "님의 남은 체력: " << player->getHealth() << endl;
		cout << monster->getName() << "의 남은 체력: ";
		if (monster->getHealth() > 0)
			cout << monster->getHealth();
		else
			cout << "0";
		cout << endl;
	}

	if (player->getHealth() <= 0) {
		gameRunning = false;
		cout << getPlayerName() << "님께서 사망하셨습니다." << endl;
	}
	else {
		cout << getPlayerName() << "님께서 전투에서 승리하셨습니다!" << endl;
	}
}

void game::tutorials()
{
	cout << "지금부터 간단한 듀토리얼을 시작하겠습니다." << endl << endl;

	while (true) {
		int championChoose = 0;
		int yesNo = 0;

		cout << "다음 기본 챔피언 중 원하는 하나를 골라 주세요." << endl << endl;
		cout << "[ 1.마스터 이 ]  [ 2.애쉬 ]  [ 3.라이즈 ]" << endl << endl;
		cout << "-> ";
		cin >> championChoose;
		cout << endl << endl << endl;

		if (championChoose == 1) {
			cout << "정말 마스터 이 챔피언으로 하시겠습니까?" << endl << endl;
			cout << "[1. 네] [2. 아니요]" << endl << endl;
			cout << "-> ";
			cin >> yesNo; cout << endl;
			cout << "-> ";
			if (yesNo == 1) {
				// 1경험치, 2사거리, 3이속, 4공격력, 5주문력, 6치확, 7공속, 8체력, 9마나, 10방어력, 11마저, 12스킬 가속, 13물관, 14마관, 15생흡, 16물리피해흡, 17모든피해흡, 18회복&보호막, 19강인함
				player = new game(0, 175, 355, 65, 0, 0, 0.679, 679, 251, 33, 32, 0, 0, 0, 0, 0, 0, 0, 0);	// 마스터이 스탯 
				cout << "마스터 이를 선택하셨군요. 마스터 이의 스탯은 다음과 같습니다." << endl << endl << endl << endl;
				nowStatus();
				break;
			}
			else if (yesNo == 2) {
				// 선택하지 않은 경우 루프
			}
		}
		else if (championChoose == 2) {
			cout << "정말 애쉬 챔피언으로 하시겠습니까?" << endl << endl;
			cout << "[1. 네] [2. 아니요]" << endl << endl;
			cout << "-> ";
			cin >> yesNo; cout << endl;

			if (yesNo == 1) {
				// 1경험치, 2사거리, 3이속, 4공격력, 5주문력, 6치확, 7공속, 8체력, 9마나, 10방어력, 11마저, 12스킬 가속, 13물관, 14마관, 15생흡, 16물리피해흡, 17모든피해흡, 18회복&보호막, 19강인함
				player = new game(0, 600, 325, 59, 0, 0, 0.658, 640, 280, 26, 0, 0, 0, 0, 0, 0, 0, 0, 0);	// 애쉬 스탯
				cout << "애쉬를 선택하셨군요.애쉬의 스탯은 다음과 같습니다." << endl << endl << endl << endl;
				nowStatus();
				break;
			}
			else if (yesNo == 2) {
				// 선택하지 않은 경우 루프
			}
		}
		else if (championChoose == 3) {
			cout << "정말 라이즈 챔피언으로 하시겠습니까?" << endl << endl;
			cout << "[1. 네] [2. 아니요]" << endl << endl;
			cout << "-> ";
			cin >> yesNo;

			if (yesNo == 1) {
				// 1경험치, 2사거리, 3이속, 4공격력, 5주문력, 6치확, 7공속, 8체력, 9마나, 10방어력, 11마저, 12스킬 가속, 13물관, 14마관, 15생흡, 16물리피해흡, 17모든피해흡, 18회복&보호막, 19강인함
				player = new game(0, 550, 340, 58, 0, 0, 0.625, 645, 300, 22, 0, 0, 0, 0, 0, 0, 0, 0, 0);	// 라이즈 스탯
				cout << "라이즈를 선택하셨군요. 라이즈의 스탯은 다음과 같습니다." << endl << endl << endl << endl;
				nowStatus();
				break;
			}
			else if (yesNo == 2) {
				// 선택하지 않은 경우 루프
			}
		}
	}
	// 1경험치, 2사거리, 3이속, 4공격력, 5주문력, 6치확, 7공속, 8체력, 9마나, 10방어력, 11마저, 12스킬 가속, 13물관, 14마관, 15생흡, 16물리피해흡, 17모든피해흡, 18회복&보호막, 19강인함

	cout << "여러 종류의 스탯은 각자 전투에 영향을 미칩니다" << endl;
	WarriorMinion warriorMinion;
	changeMonster(warriorMinion);
	fight();
	cout << "수고하셨습니다 소환사님 튜토리얼을 마칩니다." << endl << endl;
	/*Slime slime;
	changeMonster(slime);
	fight();
	*/
}

void game::run()
{
	string nameText;
	int playerChoose = 0;
	cout << "소환사의 협곡에 오신것을 환영합니다." << endl;
	cout << "소환사의 이름을 입력해 주세요." << endl << endl;
	cout << "-> ";  cin >> nameText; cout << endl;
	setPlayerName(nameText);
	cout << nameText << "님 환영합니다." << endl << endl << endl;

	tutorials();	// 듀튜리얼 시작
	// 게임에 대한 핵심 내용
	while (gameRunning)
	{

		cout << "[ 1.현재 상태 ]  [ 2.풀숲에서 아이템 찾기 ]  [ 3.풀숲에서 몬스터 찾기 ] [ 4.집으로 돌아가 재정비 ] [ 5.게임 종료 ]" << endl << endl;

		cout << "-> "; cin >> playerChoose;

		switch (playerChoose)
		{
		case 1: nowStatus(); break;
		case 2: if (rand() % 2 == 0)
		{
			cout << "아이템을 발견했다." << endl;
			getItem();
		}
			  else {
			cout << "아무것도 찾지 못했다." << endl;
		}
			  break;
		case 3: if (rand() % 2 == 0)
		{
			cout << "야생의 잡몸을 발견했다." << endl;
			fight();
		}
			  else {
			cout << "아무것도 찾지 못했다." << endl;

			break;
		case 4: cout << "집으로 돌아가 재정비를 한다." << endl;
			if (rand() % 2 == 0)
			{
				cout << "돌아가는 길에 야생의 동물을 발견!!" << endl;
				fight();
			}
			else {
				cout << "무사히 집에 돌아 왔다." << endl;
				player->setHealth(player->getHealth() + 10);
				player->setMana(player->getMana() + 10);
			}
			break;
		case 5: cout << "게임을 종료 하시겠습니까? (Y:1, N:0)>>";
			cin >> playerChoose;
			if (playerChoose == 1) gameRunning = false;
		}
		}
	}
}

// main

int main()
{
	srand(time(0));
	game* lolstat = new game();
	lolstat->run();
}
