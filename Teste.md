| | |
|:-:|:-:|
|<img src="https://via.placeholder.com/100x100" alt="Logo" width="100" height="100">|**ASASASASAS**<BR>ASASAS|
| | |

```plantuml
@startgantt
  ' *************************************************************************
  ' **                       Include Section                               **
  ' *************************************************************************
  ' Sprites 
  '!define osaPuml https://raw.githubusercontent.com/Crashedmind/PlantUML-opensecurityarchitecture2-icons/master
  '!include osaPuml/Common.puml
  '!include osaPuml/User/all.puml
  '!include osaPuml/Hardware/all.puml
  '!include osaPuml/Misc/all.puml
  '!include osaPuml/Server/all.puml
  '!include osaPuml/Site/all.puml
  !define myPuml https://raw.githubusercontent.com/GiovaniPM/PUMLSprites/refs/heads/main/files
  !include myPuml/PROGM016.puml
  !include myPuml/PROGM010.puml
  !include myPuml/PRINT001.puml
  !include myPuml/MANY.puml
  
  ' Images
  !define IMAGE_PHONE "https://giovanipm.github.io/rc_images/phone_icon.png"
  
  ' Styles
  '!define themePuml https://raw.githubusercontent.com/GiovaniPM/PUMLStyles/refs/heads/main
  '!include themePuml/styleGanttFormal1.puml
  
' *************************************************************************
' **                         Color Section                               **
' *************************************************************************
' Days
!$CLOSED_BK = "#cbe86b" /'"#006B3C"'/
!$CLOSED_LINE = white

' Task
!$ALTERNATIVE_COLOR =  Aqua/Blue
!$DONE_COLOR = lightgreen /'"#006B3C"'/
!$TASK_FONT_COLOR = "#006B3C" /'"#32CD32"'/
!$UNDONE_COLOR = "#006B3C"

' Legend
!$LEGEND_COLOR = lightgreen/white
!$LEGEND_FONT = "#006B3C"
!$LEGEND_LINE = "#006B3C"

' Milestone
!$MILESTONE_COLOR_BK = gold/green
!$MILESTONE_COLOR_FONT = "#006B3C" /'"#32CD32"'/
!$MILESTONE_COLOR_LINE = red

' Days
!$HOLIDAY_COLOR = "#cbe86b" /'"#006B3C"'/
!$TODAY_COLOR =  yellow

' Path
!$CRITICAL_PATH_COLOR = red
!$NORMAL_PATH_COLOR = "#006B3C"

' Note
!$NOTE_COLOR_BK = lightgreen/"#FFFFFF"
!$NOTE_COLOR_FONT = black
!$NOTE_COLOR_LINE = black

' Separator
!$SEPARATOR_COLOR_BK = "#006B3C"/white
!$SEPARATOR_COLOR_FONT = black
!$SEPARATOR_COLOR_LINE = black

' Time line
!$TIMELINE_COLOR = "#006B3C"/lightgreen

' Title
!$TITLE_FONT = "#006B3C"

' *************************************************************************
' **                        Style Section                                **
' *************************************************************************
' Styles 
<style>

  ganttDiagram {
    task {
      BackGroundColor $DONE_COLOR
      FontColor $TASK_FONT_COLOR
      FontName Tahoma
      FontSize 14
      FontStyle bold
      LineColor $DONE_COLOR
      'unstarted {
      '  BackGroundColor $UNDONE_COLOR
      '  LineColor $UNDONE_COLOR
      '}
    }
    'undone {
    '  BackGroundColor red
    '}
    milestone {
      BackGroundColor $MILESTONE_COLOR_BK
      FontColor $MILESTONE_COLOR_FONT
      FontName Tahoma
      FontSize 14
      FontStyle italic
      LineColor $MILESTONE_COLOR_LINE
    }
    separator {
      BackGroundColor $SEPARATOR_COLOR_BK
      FontColor $SEPARATOR_COLOR_FONT
      FontName Tahoma
      FontSize 16
      FontStyle bold
      LineColor $SEPARATOR_COLOR_LINE
    }
    note {
      BackGroundColor $NOTE_COLOR_BK
      FontColor $NOTE_COLOR_FONT
      FontName Tahoma
      FontSize 10
      HorizontalAlignment left
      LineColor $NOTE_COLOR_LINE
    }
    timeline {
      BackgroundColor $TIMELINE_COLOR
      FontStyle bold
    }
    closed {
      BackGroundColor $CLOSED_BK
      FontColor $CLOSED_FONT
    }
  }
  footer {
    HorizontalAlignment right
  }
  title {
    FontColor $TITLE_FONT
    FontName Tahoma
    FontSize 40
    FontStyle italic
    HorizontalAlignment center
  }
  legend {
    BackGroundColor $LEGEND_COLOR
    BorderRoundCorner 8
    BorderThickness 1
    FontColor $LEGEND_FONT
    FontName Tahoma
    FontStyle bold
    LineColor $LEGEND_LINE
  }

</style>

skinparam footerFontColor $TITLE_FONT
skinparam footerFontSize 12
skinparam footerFontStyle italic
'skinparam titleBackgroundColor Aqua-CadetBlue
'skinparam titleBorderColor blue
'skinparam titleBorderRoundCorner 15
'skinparam titleBorderThickness 2
  
  ' *************************************************************************
  ' **                        Setup Section                                **
  ' *************************************************************************
  ' Variables
  !$caption = 'Cronograma'
  !$now = %now()
  !$nowbr = %date("dd/MM/YYYY HH:mm:ss", $now - 3*3600)
  !$projectName = 'Project Name'
  
  ' Initialization
  caption $caption                                                           /'Gantt caption'/
  title $projectName                                                         /'Project Name'/
  footer $projectName\n$nowbr                                                /'Footer message'/
  'hide footbox                                                               /'Hide foot timeline'/
  project starts 2025/01/01                                                  /'When project starts YYYY/MM/DD'/
  scale 1                                                                    /'Project zoom'/
  'Label on last column and left aligned                                      /'Task appear in the gantt begin'/
  'Label on first column and left aligned                                     /'Task appear in the gantt end'/
  language pt                                                                /'language'/
  'hide resources names                                                       /'Hide the ressources names in the name task'/
  'hide resources footbox                                                     /'Hide the ressources'/
  
  ' Project Scale                                                            /'How the scale coluns will showed in the gant'/
  printscale daily zoom 1.5
  'printscale quarterly zoom 20
  'printscale weekly zoom 6
  
  ' Day watching                                                             /'Day viewed in the gant'/
  'today is YYYY/MM/DD and is colored in $TODAY_COLOR
  'today is 14 days after start and is colored in $TODAY_COLOR
  today is colored in $TODAY_COLOR
  
  ' Working Closed Days                                                      /'Days not worked'/
  'YYYY/MM/DD is closed
  'YYYY/MM/DD to YYYY/MM/DD is closed
  saturday are closed
  sunday are closed
  '************2025************
  2025/01/01 is closed                                                       /'Ano novo'/
  2025/01/01 are colored in $HOLIDAY_COLOR
  2025/02/02 is closed                                                       /'Navegantes'/
  2025/02/02 are colored in $HOLIDAY_COLOR
  '2025/04/18 is closed                                                       /'Sexta-feira santa'/
  '2025/04/18 are colored in $HOLIDAY_COLOR
  '2025/04/20 is closed                                                       /'Tiradentes'/
  '2025/04/20 are colored in $HOLIDAY_COLOR
  '2025/05/01 is closed                                                       /'Trabalho'/
  '2025/05/01 are colored in $HOLIDAY_COLOR
  '2025/09/07 is closed                                                       /'Independencia'/
  '2025/09/07 are colored in $HOLIDAY_COLOR
  '2025/10/12 is closed                                                       /'Aparecida'/
  '2025/10/12 are colored in $HOLIDAY_COLOR
  '2025/11/02 is closed                                                       /'Finados'/
  '2025/11/02 are colored in $HOLIDAY_COLOR
  '2025/11/15 is closed                                                       /'Proclamação'/
  '2025/11/15 are colored in $HOLIDAY_COLOR
  '2025/11/20 is closed                                                       /'Consciencia'/
  '2025/11/20 are colored in $HOLIDAY_COLOR
  '2025/12/25 is closed                                                       /'Natal'/
  '2025/12/25 are colored in $HOLIDAY_COLOR
  
  ' Colored Days                                                              /'Coloring days in the gant'/
  'YYYY/MM/DD is colored in lightblue
  'YYYY/MM/DD to YYYY/MM/DD are colored in Orange
  
  ' *************************************************************************
  ' **                         Task Section                                **
  ' *************************************************************************
  ' Tasks and separators
  -- Phase One --
  [Prototype design] on {Alice} lasts 13 days
    [Prototype design] links to [[http://plantuml.com]]
    note bottom
      <$PROGM016>
      Key user not send purchase requests
      Image here: [[IMAGE_PHONE]]
    end note
  [Config prototype] on {Giovani} lasts 7 days
  -- Phase Two --
  [QA prototype] on {Davi} lasts 9 days
  [Test prototype] on {Camila:50}{Giovani:50} lasts 6 days
    [Test prototype] pauses on monday
    [Test prototype] pauses on friday
  -- Phase Three --
  [Deploy] lasts 1 day
  [PD audict] lasts 10 days
  [Trainning] on {Camila:50}{Maria:50} starts 2025/01/20
    [Trainning] ends 2025/02/14
  
  ' Tasks flow
  [Config prototype] starts at [Prototype design]'s end with $NORMAL_PATH_COLOR bold link
  [QA prototype] starts at [Prototype design]'s end with $CRITICAL_PATH_COLOR bold link
  [Test prototype] starts at [Config prototype]'s end with $NORMAL_PATH_COLOR bold link
    [Test prototype] starts at [QA prototype]'s end with $CRITICAL_PATH_COLOR bold link
  [Deploy] starts at [Test prototype]'s end with $CRITICAL_PATH_COLOR bold link
  [PD audict] starts at [Trainning]'s end with $NORMAL_PATH_COLOR bold link
    [PD audict] starts at [Deploy]'s end with $CRITICAL_PATH_COLOR bold link
  
  ' Tasks deleted
  [Config prototype] is deleted
  
  ' Tasks colors alternatives
  [Trainning] is colored in $ALTERNATIVE_COLOR
  
  ' Tasks progress
  [Prototype design] is 75% completed
  [Config prototype] is 50% completed
  [QA prototype] is 50% completed
  [Test prototype] is 20% completed
  [Deploy] is 0% completed
  [PD audict] is 0% completed
  [Trainning] is 50% completed
  
  ' Milestones
  -- Milestones --
  [DevEnd] happens at [Prototype design]'s end
    [DevEnd] happens at [QA prototype]'s end
  [ReadyDeploy] happens at [Test prototype]'s end
    [ReadyDeploy] displays on same row as [DevEnd]
  [PDEnd] happens at [PD audict]'s end
    [PDEnd] displays on same row as [ReadyDeploy]
  -- End --
  
  legend left
    Legend:
    |= Color                 |= Type           |
    |<#$DONE_COLOR>          | Done            |
    |<#$CRITICAL_PATH_COLOR> | Critic Path     |
    |<#blue>                 | Outside IT      |
    |<#black>                | Deleted task    |
  end legend
@endgantt
```