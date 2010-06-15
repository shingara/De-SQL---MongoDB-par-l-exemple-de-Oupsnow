!SLIDE

# Sous SQL #
## 10 Tables ##

!SLIDE

# Sous MongoDB #
## 8 Collections ##

!SLIDE

# Où sont passés les 2 tables ? #

!SLIDE

# Les documents embarqués !! #

!SLIDE

# Les relations N-N #

!SLIDE

# Plus de table de liaison. #
# On embarque le document de liaisons #

!SLIDE Center

# En SQL #
## Table de liaison de ##
## User - Project - Function ##

### function_id
### user_id
### project_id

!SLIDE

# En MongoDB #
## Collection Project ##

    @@@ruby

    project_member =>
      { :function_id => 'xxx',
        :user_id => 'xxx',
        :project_id => 'xxx'}

!SLIDE

# Quel question se poser #
# pour choisir son schéma ? #

!SLIDE

# Pas de jointure alors comment faire ? #

!SLIDE

# On a une application en REST #

!SLIDE

# Une resource #
# == #
# un document MongoDB #
