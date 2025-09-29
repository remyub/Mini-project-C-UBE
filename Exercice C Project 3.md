1°)

#include <stdio.h> 
#include <string.h> 

int main() 
{ 
  char article[20]; 
  printf("Saisir un article : \n"); 
  fgets(article, 20, stdin); 
  printf("Article ajouté \n") 
  return 0; 
}

2°)

#include <stdio.h>
#include <string.h>

int main() 
{
    int n=0;
    printf("Saisir le nombre d'article souhaité : \n ");
    scanf("%d", &n);
    getchar();
    if (n==0)
        return 0;
    else if (n>10)
        {
        printf("Trop d'article, ne pas dépasser 10 \n");
        return 0;
        }
    char article[n][20];  //selon l'ia cela peut passer avec certain compilateur sinon mettre article[10][20]
        for (int i=0; i<n;i++)
        {
            printf("Saisir l'article numéro %d : \n", i+1);
            fgets(article[i], 20, stdin);
        }
    printf("Voici la liste d'article : \n ");
    for (int j=0; j<n; j++)
        printf("%s \n", article[j]);
    return 0;
}

3°)

#include <stdio.h>
#include <string.h>

int main()
{
    char mode[20];
    char article[10][20]; 
    int nbArticles = 0; 
    printf("Afficher , Ajouter , Effacer. \n");
    scanf("%19s", mode);
    getchar();
    if (strcmp(mode, "Ajouter") == 0)
        {
            int n=0;
            printf("Saisir le nombre d'article souhaité : \n ");
            scanf("%d", &n);
            getchar();
            if (n==0)
                return 0;
            else if (n>10)
                {
                printf("Trop d'article, ne pas dépasser 10 \n");
                return 0;
                }  
                for (int i=0; i<n;i++)
                {
                    printf("Saisir l'article numéro %d : \n", i+1);
                    fgets(article[i], 20, stdin);
                }
                nbArticles=n;
        }
    else if (strcmp(mode, "Afficher") == 0)
        {
            printf("Voici la liste d'article : \n ");
            for (int j=0; j<nbArticles; j++)
            printf("%s \n", article[j]);
        }
    else if (strcmp(mode, "Effacer") == 0)
        {
             int m=0;
             printf("Saisir le nombre d'article à supprimer : \n ");
             scanf("%d", &m);
             if (m==0)
                 return 0;
             else if (m>10)
                 {
                 printf("Trop d'article, ne pas dépasser 10 \n");
                 return 0;
                 }
            for (int k = m - 1; k < nbArticles - 1; k++)
            {
                strcpy(article[k], article[k + 1]);
            }
            nbArticles--;
        }
    else 
        printf("Erreur de saisie. \n");
    
    return 0;
}
