1°)
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Etudiant {
    char nom[30];
    int age;
    float note;
};

int main(){
    struct Etudiant e;
    printf("Veuillez saisir votre nom, age et note : \n");
    scanf("%s %d %f",&e.nom ,&e.age ,&e.note);
    printf("Nom : %s \n Age : %d \n Note : %.2f \n", e.nom, e.age, e.note);
    return 0;
}

2°)
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Etudiant {
    char nom[30];
    int age;
    float note;
};

int main(){
    int n;
    printf("Veuillez saisir le nombre d'étudiant (max20) : \n");
    scanf("%d",&n);
    struct Etudiant e[n];
    for(int i=0;i<n;i++){
        printf("Veuillez saisir le nom, l'age et la note de l'étudiant %d : \n", i+1);
        scanf("%s %d %f",&e[i].nom ,&e[i].age ,&e[i].note);
    }
    for(int i=0;i<n;i++){
        printf("Nom : %s , Age : %d , Note : %.2f \n", e[i].nom, e[i].age, e[i].note);
    }
    return 0;
}

3°)
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Etudiant {
    char nom[30];
    int age;
    float note;
};

int main(){
    int n;
    printf("Veuillez saisir le nombre d'étudiant (max20) : \n");
    scanf("%d",&n);
    struct Etudiant e[n];
    FILE *f;
    f=fopen("etudiants.txt","w");
    if(f==NULL){
        printf("Erreur d'ouverture du fichier \n");
        return 1;
    }
    
    for(int i=0;i<n;i++){
        printf("Veuillez saisir le nom, l'age et la note de l'étudiant %d : \n", i+1);
        scanf("%s %d %f",&e[i].nom ,&e[i].age ,&e[i].note);
    }
    for(int i=0;i<n;i++){
        printf("Nom : %s , Age : %d , Note : %.2f \n", e[i].nom, e[i].age, e[i].note);
        fprintf(f,"Nom : %s , Age : %d , Note : %.2f \n", e[i].nom, e[i].age, e[i].note);
    }
    fclose(f);
    return 0;
}
