# -*- coding: utf-8 -*-

from MaBase_MIB import *

### Question 1 : quel est l'ensemble des gardiens?
les_gardiens = {gardien.Nom for gardien in BaseGardiens}
### Question 2 : quel est l'ensemble des villes d'origine des agents?
les_villes_agents = {agent.Ville for agent in BaseAgents}

les_villes_agents
{'Hesperos', 'Kalgan', 'Terminus', 'Uco'}
### Question 3 : quel est l'ensemble des triplets (no de cabine,alien,gardien) pour chaque cabine?
triples = { (alien.NoCabine, alien.Nom, gardien.Nom) for alien in BaseAliens  for gardien in BaseGardiens if gardien.NoCabine == alien.NoCabine}


{('1', 'Zorglub', 'Branno'),
 ('2', 'Blorx', 'Darell'),
 ('3', 'Urxiz', 'Demerzel'),
 ('4', 'Darneurane', 'Seldon'),
 ('4', 'Zbleurdite', 'Seldon'),
 ('6', 'Mulzo', 'Hardin'),
 ('7', 'Zzzzzz', 'Trevize'),
 ('8', 'Arghh', 'Pelorat'),
 ('9', 'Joranum', 'Riose')}
### Question 4 : quel est l'ensemble des couples (alien,allée) pour chaque alien?
couple = {(Alien.Nom, allee.NoAllee) for Alien in BaseAliens for allee in BaseCabines if Alien.NoCabine==allee.NoCabine}
### Question 5 : quel est l'ensemble de tous les aliens de l'allée 2?
allee2={ (alien.Nom) for alien in BaseAliens for cabine in BaseCabines if alien.NoCabine==cabine.NoCabine and cabine.NoAllee=='2'}

### Question 6 : quel est l'ensemble de toutes les planètes dont sont originaires les aliens habitant une cellule de numéro pair?
aliensP={ (alien.Planete) for alien in BaseAliens if float(alien.NoCabine)%2==0 }

### Question 7 : quel est l'ensemble des aliens dont les gardiens sont originaires de Terminus?
gardienT={ (alien.Nom) for alien in BaseAliens for gardien in BaseGardiens for agent in BaseAgents if alien.NoCabine==gardien.NoCabine and gardien.Nom==agent.Nom and agent.Ville=='Terminus'}

### Question 8 : quel est l'ensemble des gardiens des aliens féminins qui mangent du bortsch?
gardienB = { (Gardien.Nom) for Gardien in BaseGardiens for Alien in BaseAliens for Miam in BaseMiams if Miam.Aliment=='Bortsch' and Miam.NomAlien==Alien.Nom and Alien.Sexe=='F' and Alien.NoCabine==Gardien.NoCabine }

### Question 9 : quel est l'ensemble des cabines dont les gardiens sont originaires de Terminus ou dont les aliens sont des filles?
gardienF={ (cabine.NoCabine) for cabine in BaseCabines for gardien in BaseGardiens for alien in BaseAliens for agent in BaseAgents if (gardien.Nom==agent.Nom and agent.Ville=='Terminus' and gardien.NoCabine==cabine.NoCabine) or (alien.Sexe=='F' and alien.NoCabine==cabine.NoCabine) }

### Question 10 : Y a-t-il des aliments qui commencent par la même lettre que le nom du gardien qui surveille l'alien qui les mange ?
lettreN={ (gardien.Nom,miam.Aliment) for gardien in BaseGardiens for miam in BaseMiams for alien in BaseAliens if miam.NomAlien==alien.Nom and alien.NoCabine==gardien.NoCabine and miam.Aliment[0]==gardien.Nom[0] }

### Question 11 : Y a-t-il des aliens originaires d'Euterpe ?
aliensE={ (alien.Nom) for alien in BaseAliens if alien.Planete=='Euterpe' }

### Question 12 : Est-ce que tous les aliens ont un 'x' dans leur nom?
xna = {(Alien.Nom) for Alien in BaseAliens if 'x' in Alien.Nom }
an = 'Alien.Nom'
k = an.count('x')
if (k==9):
    print("12) tout les aliens ont des x dans leur noms",xna)

else :
    print("12) tout les aliens n'ont pas de x dans leur noms, voici ceux qui en ont :", xna)
### Question 13 : 13- Est-ce que tous les aliens qui ont un 'x' dans leur nom ont un gardien qui vient de Terminus ?
agt = {(Alien.Nom, Agent.Nom) for Alien in BaseAliens for Gardien in BaseGardiens for Agent in BaseAgents if 'x' in Alien.Nom if Agent.Ville == 'Terminus' if Agent.Nom == Gardien.Nom if Gardien.NoCabine == Alien.NoCabine}

if (xna == agt):
    print("13) tout les aliens qui ont un x dans leur nom ont des gardiens qui viennent de Terminus, les voici :", agt)
else :
    print("13) tout les aliens qui ont un x dans leur nom n'ont pas des gardiens venant de Terminus, les voici :", agt)
### Question 14 : 14- Existe-t-il un alien masculin originaire de Trantor qui mange du Bortsch ou dont le gardien vient de Terminus ?
zy = {(Alien.Nom) for Alien in BaseAliens for Miam in BaseMiams if Alien.Sexe == 'M' if Alien.Planete == 'Trantor' if Alien.Nom == Miam.NomAlien if Miam.Aliment == 'Bortsch'}
zz = {(Alien.Nom) for Alien in BaseAliens for Gardien in BaseGardiens for Agent in BaseAgents if Alien.Sexe == 'M' if Alien.Planete == 'Trantor' if Alien.NoCabine == Gardien.NoCabine if Gardien.Nom == Agent.Nom if Agent.Ville == 'Terminus'}

if (zy == zz) :
    print ("14) il(s) existe(s) un alien(s) masculin originaire de Trantor qui mange du Bortsch ou dont le gardien vient de Termnius, le(s) voici :", zz)
else :
    print ("14) il existe un alien masculin originaire de Trantor qui mange du Bortsch ou dont le gardien vient de Terrminus, le voici :",
    zy, zz)
