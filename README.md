#include <iostream>
#include <vector>
#include <algorithm>
#include <string>
using namespace std;
class Character {
protected:
 string name;
 int level;
 int health;
public:
 Character(string n, int l=1, int h=100): name(n), level(l), health(h) {}
 virtual void useSpecialAbility() = 0;
 virtual ~Character() { cout << name << " destroyed\n"; }
 int getLevel() { return level; }
 string getName() { return name; }
};
// Virtual inheritance to prevent multiple Character copies
class Warrior : virtual public Character {
protected:
 int attackPower;
 vector<string> weapons;
public:
 Warrior(string n, int ap=50) : Character(n), attackPower(ap) {}
 Warrior& equip(string w) { weapons.push_back(w); return *this; }
 void useSpecialAbility() override { cout << name << " performs a powerful attack!\n"; }
};
class Mage : virtual public Character {
protected:
 int mana;
 vector<string> spells;
public:
 Mage(string n, int m=100) : Character(n), mana(m) {}
 Mage& learnSpell(string s) { spells.push_back(s); return *this; }
 void useSpecialAbility() override { cout << name << " casts a spell!\n"; }
};
class Healer : virtual public Character {
protected:
 vector<string> potions;
public:
 Healer(string n) : Character(n) {}
 Healer& addPotion(string p) { potions.push_back(p); return *this; }
 void useSpecialAbility() override { cout << name << " heals an ally!\n"; }
};
// Hybrid Classes
class Paladin : public Warrior, public Healer {
public:
 Paladin(string n): Character(n), Warrior(n), Healer(n) {}
 void useSpecialAbility() override { cout << name << " smites evil and heals!\n"; }
};
class BattleMage : public Warrior, public Mage {
public:
 BattleMage(string n): Character(n), Warrior(n), Mage(n) {}
 void useSpecialAbility() override { cout << name << " attacks and casts magic!\n"; }
};
