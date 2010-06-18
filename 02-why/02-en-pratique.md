!SLIDE

# Mais ca donne quoi ce changement ? #

!SLIDE

# Avant #

!SLIDE

# Sous SQL #
## 10 Tables ##

!SLIDE

# Après #

!SLIDE

# Sous MongoDB #
## 8 Collections ##

!SLIDE

# Mais une collection == table ? #

!SLIDE

# Où sont passés 2 tables ? #

!SLIDE

# Les documents embarqués !! #

!SLIDE

# Où les utiliser ? #

!SLIDE

# Les relations N-N #

!SLIDE

# Plus de tables de liaisons. #
# On embarque le document de liaisons #
# dans le document "maitre" #

!SLIDE

# Exemple de la table de liaison entre #
## Un utilisateur ( users) ##
## Une fonction ( functions ) ##
## Un projet ( projects ) ##


!SLIDE Center

# En SQL #
## La table de liaison contient ##

### function_id
### user_id
### project_id

!SLIDE

# Où embarquer le document ? #

!SLIDE

# Le maître est le projet. #
# C'est lui qui veux connaitre ses membres #

!SLIDE

# En MongoDB #
## Collection Project ##

    @@@ruby

    project_member =>
      { :function_id => 'xxx',
        :user_id => 'xxx'}

!SLIDE

# Mais pour les liaisons inverses ? #

!SLIDE small

    @@@ ruby

    def projects
      Project.all(:conditions =>
          {'project_members.user_id' => self.id})
    end

!SLIDE small

    @@@ ruby

    def projects
      Project.all(:conditions =>
          {'project_members.user_id' => self.id})
    end

!SLIDE

# Quel question se poser #
# pour choisir son schéma ? #

!SLIDE

# Problème de MongoDB #

!SLIDE

# Pas de jointure #

!SLIDE

# Si on veux deux documents, il faut faire 2 requêtes #

!SLIDE

# Alors pourquoi ne pas vouloir qu'un document ? #

!SLIDE

# Rappel : #

!SLIDE

# On a une application en REST #

!SLIDE

# et si #

!SLIDE

# Une resource #
# == #
# un document MongoDB  ? #

!SLIDE

# Une vue de ressource #
# == #
# Une requête #

!SLIDE

# Il faut donc dénormaliser #

!SLIDE

# Facile MongoDB SchemaLess #

!SLIDE

# On peux donc ajouter autant d'information à la volé dans notre document #

!SLIDE

# exemple : #

!SLIDE

# On veux la page de visualisation d'un utilisateur #

!SLIDE

# Dedans on veux les noms des projets sur lequel il appartient #

!SLIDE

# Embarquons cette information dans le document User #

!SLIDE

# On a donc un Array contenant la liste des noms des projets auquel l'utilisateur appartient #

!SLIDE

# Attention #

!SLIDE

# Il faut un maitre des données qui mette à jour les autres le moment venu #
