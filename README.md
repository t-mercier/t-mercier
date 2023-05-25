#### My software engineer journey as a (simple) C program ...

```c
#include <stdbool.h>
#include <stdlib.h>

#define SUCCESS 1
#define FAILURE 0
#define PROJECTS 27
#define XP_PER_LEVEL 500

typedef struct s_dev {
    size_t days;
    int difficulty;
    bool succeed;
} t_dev;

typedef struct s_study {
    char *school;
    char *situation;
    char *languages;
    char *contact;
} t_study;

typedef struct s_student {
    t_dev project;
    t_study infos;
    int level;
    int motivation;
    int frustration;
    int xp;
    size_t blackhole;
} t_student;

t_student init_student() {
    t_student student = {
        .project = {0, 1, false},
        .infos = {
            .school = "CODAM | 42Amsterdam", 
            .situation = "studying software engineering",
            .languages = "C && C++", 
            .contact = "contact@mercier.app",
        }, 
        .level = 4.31,
        .motivation = 100, 
        .frustration = 0
        .blackhole = 900,
        .xp = 0,
    };
    return student;
}

int study(t_dev *project, int level){
    return (level >= project->difficulty) ? SUCCESS : FAILURE;
}

int student_progress(t_student *student){
    int rush_adrenaline = 0;
    while (!student->project.succeed && student->blackhole--) {
        student->project.succeed = (study(&student->project, student->level) == SUCCESS);
        rush_adrenaline += (student->project.succeed) ? 1 : -1;
        student->frustration += (!student->project.succeed) ? 1 : 0;
        student->xp += (student->project.succeed) ? 100 : 0;
        if (student->xp >= student->level * XP_PER_LEVEL) {
            student->xp = 0;
            student->level++;
            student->motivation++;
        }
        student->project.days++;
    }
    return rush_adrenaline;
}

void    try_project(t_student *student){
    t_dev p[PROJECTS] = {0};
    int holidays = 3; 
    
    for (int i = 0; i < PROJECTS; i++){
        timothee.project = p[i];
        student.motivation += student_progress(timothee);
        if (timothee.frustration < timothee.motivation){
            continue ;
        take_break(timothee)
        if (!holidays--)
            break ;
    }
}

int main(){
    t_student timothee = init_student();
   
    while (1){
        try_project(&timothee);
        if (timothee.blackhole == 0)
            exit(FAILURE);
    }
    return 0;
}

```
<table>
    <tr>
        <th>Progress Tracking</th>
        <th>Projects</th>
        <th>Dev</th>
        <th>Design</th>
    </tr>
    <tr>
        <td style="text-align: center;">
            <a href="https://github.com/JaeSeoKim/badge42"><img src="https://badge42.vercel.app/api/v2/clafi69q000590fmnc94ufq04/stats?cursusId=21&coalitionId=59" alt="tmercier's 42 stats" /></a>
        </td>
        <td style="text-align: center">
            <div style="text-align: center;">
                <a href="https://github.com/t-mercier/42_philosophers" title="Repository"><b>PHILOSOPHER</a><br />
                <a href="https://github.com/t-mercier/42_minishell" title="Repository">MINISHELL</a><br />
                <a href="https://github.com/t-mercier/42_minitalk" title="Repository">MINITALK</a><br />
                <a href="https://github.com/t-mercier/42_fdf" title="Repository">FDF</a><br />
                <a href="https://github.com/t-mercier/42_push_swap" title="Repository">PUSH_SWAP</a><br />
                <a href="https://github.com/t-mercier/42_born2beroot" title="Repository">BORN2BEROOT</a><br />
                <a href="https://github.com/t-mercier/42_libs" title="Repository">GET_NEXT_LINE</a><br />
                <a href="https://github.com/t-mercier/42_libs" title="Repository">PRINTF</a><br />
                <a href="https://github.com/t-mercier/42_libs" title="Repository">LIBFT</a>
            </div>
        </td>
        <td style="text-align: center;">
            <div style="line-height: 2;">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="c" width="40" height="40" /><br />
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" alt="cplusplus" width="40" height="40" /><br />
                    <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git" width="40" height="40" /><br />
            </div>
        </td>
        <td style="text-align: center;">
            <div style="line-height: 2;">
                <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma" width="40" height="40" /><br />
                <img src="https://www.vectorlogo.zone/logos/adobe_illustrator/adobe_illustrator-icon.svg" alt="illustrator" width="40" height="40" /><br />
                <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt="photoshop" width="40" height="40" /><br />
                <img src="https://cdn.worldvectorlogo.com/logos/adobe-xd.svg" alt="xd" width="40" height="40" />
            </div>
        </td>
    </tr>
</table>
