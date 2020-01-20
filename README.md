#include <stdio.h>
#include <stdlib.h>
//utilisation des symboles pour faciliter l'ecriture et l'ecriture du programme
#define Roi_Blanc 1
#define Pion_Blanc 2
#define Dame_blanche 3
#define Roi_Noir -1
#define Pion_Noir -2
#define Dame_Noir -3
#define case_royal 4
#define case_horizontal 5
#define case_vertical 6
#define bute 7
#define case vide 0
//la structure case qui symbolise une case  a pour champs deux entiers une pour la ligne et l'autre pour la colonne
typedef struct{
int lig ,col;
}case;
//structure deplassement possede deux elements ,deux cases une etant la case initial et l'autre case final
typedef struct{
case case_i,case_f;
}deplacement;
//structure element qu'est un element d'une liste chaityp
struct element{
case c;
listecases *suivant;
};
//structure joueur qui symbolise un joueur a pour champs son nom ,sa couleur ,ainsi celle des pions et dames, et son type
typedef struct {
char *nom;
int type;
int couleur;
}joueur;
//stuctrure presente le jeu
typedef struct {
int plateau[15][15];//represente l'etat du tableau
int nbp_noir ;//nombre de pions noirs
int nbd_noir ;//nombre de dames noirs
int nbp_blanc ;//nombre de pions blanc
int nbd_balnc ;//nombre de dame blanche

}bulltricker;
void initialisation(bulltricker*jeu)
int i,j;
jeu->nbp_noir=15;
jeu->nbp_blanche=15;
jeu->nbd_noir=8;
jeu->nbd_blanche=8;
//cases royals
plateau[1][8]=1;
plateau[13][8]=-1;
for(j=0;j<15;j++){
        if(j%2==0){
            jeu-> plateau[1][j]=3;
            jeu->plateau[13][j]=-3;
            jeu-> plateau[3][j]=2;
            jeu-> plateau[11][j]=-2;
             else {
               jeu-> plateau[1][j]=0 ;
               jeu-> plateau[3][j]=0;
               jeu-> plateau[2][j]=2;
               jeu->plateau[13][j]=0;
               jeu->plateau[11][j]=0;
               jeu-> plateau[12][j]=-2;


             }
        }


}
for(i=5;i<12;i=++){
   for(j=0;j<15;j++) {
   jeu-> plateau[i][j]=0;
   }
}
//fonction presente les differentes choix de deplecement des pions
void deplacement_pions (bulltricker*jeu,deplacement*d)
int j,i=3;
jeu->plateau[d->case_i.lig][d->case_i.col]=jeu->plateau[i][j]
for(i=3;i<=14;i++){
    for(j=0;j<=14;j++){
        jeu->plateau[d->case_f.lig][d->case_f.col]=jeu->plateau[i+1][j+1]||jeu->plateau[d->case_f.lig][d->case_f.col]=jeu->plateau[i+1][j-1]||
        jeu->plateau[d->case_f.lig][d->case_f.col]=jeu->plateau[i+2][j];

        }



}
//fonction presente des differentes choix de deplecement des deux roix
void deplacement_roi(bulltricker*jeu,deplacement*d){
    case*c;
    int choix;
    int i,j;
    i=j=1;
    jeu->plateau[d->case_i.lig][d->case_i.col]=jeu->plateau[i][j];
    while(jeu->plateau[d->case_i.lig][d->case_i.col]=4&& i<=14){
                switch(choix){
            case 1:
               jeu->plateau[d->case_f.lig][d->case_f.col] =jeu->plateau[i][j-2];

            case 2:
               jeu->plateau[d->case_f.lig][d->case_f.col] =jeu->plateau[i][j+2];
            case 3:
                jeu->plateau[d->case_f.lig][d->case_f.col] =jeu->plateau[i+2][j];
            case 4:
                jeu->plateau[d->case_f.lig][d->case_f.col] =jeu->plateau[i-2][j];
                }
            }
        }
