#!/usr/bin/env bash


count_files() {
    ls -1 | wc -l
}


number_of_files=$(count_files)

echo "Devinez combien de fichiers se trouvent dans le répertoire courant :"


while true
do
    read user_guess

    if [[ $user_guess -lt $number_of_files ]]
    then
        echo "Votre estimation est trop petite. Réessayez :"
    elif [[ $user_guess -gt $number_of_files ]]
    then
        echo "Votre estimation est trop grande. Réessayez :"
    else
        echo "Bravo ! Vous avez deviné le bon nombre 🎉"
        break
    fi
done
