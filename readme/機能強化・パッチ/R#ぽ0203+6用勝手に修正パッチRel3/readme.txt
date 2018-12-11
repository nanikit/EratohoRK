_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
·명칭			R#0203+6용 마음대로 수정 패치 Rel3
·동작환경		eratohoReverse# 0203 test판+6
·작자			/L
·배포원		http://ux.getuploader.com/aba98725/
_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#

[수정 내용]
EVENT_K.ERB
　　1@KOJO_REACT에 콤비 네이션 REACT 및 파생원을 호출하는 처리를 추가
ACT_APLLY.ERB
　　1@ACTION_APPLY2_5에 있어서 REACT 분류의 잘못이라고 생각되는 것을 수정
ACT_MESSAGE.ERB
　　1@TRAIN_MESSAGE_12에 있어서 RAND:2를 T_COND("정욕")로 변경
　　2@TRAIN_MESSAGE_14에 대해 불필요한 공행이라고 생각되는 것을 삭제
　　3@TRAIN_MESSAGE_34에 있어서, 의미 불명한 하늘의 PRINTFORML를 올바르다고 생각되는 형태에 수정
　　4. 성교 봉사계@TRAIN_MESSAGE에 대해@V_SEX가 TARGET를 참조하고 있던 것을 MASTER에 수정
　　5@TRAIN_MESSAGE_99에 있어서 대입되어 있지 않은 ACT 파생을 참조하고 있는 것을 수정
　　6@TRAIN_MESSAGE_303에 있어서 탈자를 수정
　　7@TRAIN_MESSAGE2_5에 있어서, 하위의 분기의 방해가 된다고 생각되는 ELSEIF ACTION_APPLY2_5 V(-1) == 2를 comment out
　　8. 수정 시에 함께 치환되어 버렸다고 생각되는 공행용의 PRINTFORML를 PRINTL에
　　9. 코피페 시에 어긋났다고 생각되는 인덴트를 수정
SOURCE_MESSAGE.ERB
　　1. 콤비 네이션에 파생 할 수 있는 개소의 IS_NOWACTNAME를 GET_ACTNAME(GET_NORMALACTNUM(TFLAG:ACT))에
　　2. 조수 협력시의 CFLAG:ASSI:조조방침 == 1을 TCVAR:(ASSI:1):조수 방침 == GET_ASSIMENUNUM("콤비 네이션")에

[Rel2. 수정 내용]
COMMON_GETTER_TRAIN.ERB
　　1. REACT 인상 관련 함수군
　　　@COMIMPLIST/@GET_COMIMPNAME/@COMIMPNAME/@GET_COMIMPNUM/@COMIMPNUM/@NOWCOMIMPNAME/@IS_NOWCOMIMPNAME/@IS_COMIMPNAME
　　　이상의 것을 추가
ACT_MESSAGE.ERB
　　1@TRAIN_MESSAGE2_40에 있어서 수용이 되는 개소에 REACT 분류:받아들임을 추가 후, 적극적 따르면 병렬처리
　　2@TRAIN_MESSAGE2_45에 있어서 수용이 되는 개소에 REACT 분류:받아들이는 것을 추가
ACT_APPLY.ERB
　　1@ACTION_APPLY2_57에 있어서 수용이 되는 개소에 REACT 분류:소극적 따르는 것을 추가
　　　거절이 되는 분기에 REACT 분류:거부를 추가
　　2@ACTION_APPLY2_90에 있어서 IS_NOWCOMNAME("자위하기 시작한다")의 개소의 SET_COMGRO("거부")를 comment out
　　3@ACTION_APPLY_92에 있어서 COM 도구를 제외하는 것으로 날뛰는 취급이 될 수 있는 TEQUIP 해제 처리를 추가 후 comment out
　　　(본체측의 판단에 맡기고 싶은 의향)
COM_00.ERB
　　1@COM1에 있어서 애원이 되는 분기 조건에 IS_NOWACTNAME("매도")를 추가
　　2@COM7에 있어서 REACT 파생 = 0의 처리를 ELSE 이후에 실시하도록(듯이)
COM_10.ERB
　　1@COM11에 있어서 ACT:역강간때 REACT 분류:날뛰는이 되지 않게 수정
COM_30.ERB
　　1@COM32에 있어서 ACT:역강간때 REACT 분류:날뛰는이 되지 않게 수정
　　2@COMM33에 있어서 REACT 파생 = 0의 처리를 ELSE 이후에 실시하도록(듯이)
COM_50.ERB
　　1@COM50 파생:마음대로 자위 하지마 라고 되는 개소의 조건에 MENUMATCH(TFLAG:ACT, "봉사")와 IS_NOWACTNAME("쉬게 한다")를 추가
　　　SET_COMGRO/SET_COMIMP의 처리를 파생마다 분리. 파생 1은 SET_COMGRO("거부")/SET_COMIMP("악인상대")에
　　　의존도 변화 처리도 별도 추가
REACTION_MESSAGE.ERB
　　1. CA%TSTR:2%SE 4, 강하게 응답하는 것 REACT 파생 대입 처리를 comment out(@COM4로 대입을 하고 있기 때문에(위해))
　　2. CASE 7, 허가를 청하는 것 부하 2가 납득 가지 않았기 때문에 수정
　　3. CASE 12, 서투르다고 매도하는 것에 있어서 TFLAG:REACT 인상을 IS_COMIMPNAME에
　　4. CASE 14, 쾌감을 참는 것에 있어서 부하 2/COMCOR_POSI()의 개소가 납득 가지 않았기 때문에 수정
　　5. CASE 30, 아픔을 참는 것에 있어서 ACT:이라마치오 또한 부하 0의 경우 「이빨을 이를 악문다」라고 되는 것을 회피하도록(듯이) 수정
　　6. CASE 70, 가게 해에 있어서 REACT 파생 0 상당한 분기가 없었기 때문에 추가

[Rel3. 수정 내용]
COMMON_GETTER_CHARA.ERB
　　1@AFFECTION에 정의 "공포", "반항"을 추가, 및 미정도리로 에러 초월할 때(%ARGS%)로 내용을 주울 수 있도록(듯이)
EVENT_DAYLY.ERB
　　1. DAILY_LIFE_NURSING에 ARG:1(피로로 조교 중지가 되었을 경우)을 추가
　　　구상측은 일상 이벤트@KOJO_EVENT_KX_201(ARG)에 있어서 IF LOCAL && ARG == 1으로 기술하는 것이 가능
ROUTINE.ERB
　　1. FLAG:END 달성에의 대입을 RESULT치 0이상으로 실시하도록(듯이)
EVENTCOMEND.ERB
　　1. 조교 종료의 판정 시에 FLAG:일상 제어를 리셋트 하도록(듯이)
EVENTRAIN.ERB
　　1. 대만족 보너스 관련을 손질
　　　"%CALLNAME:TARGET%님대만족 보너스"의 표시가 눈에 띄도록(듯이) 변경
　　　KOJO_EVENT(16) 뒤로 PRINTL로 공행이 들어가도록(듯이)
　　　CFLAG:만족 보의 리셋트를 오늘의 방침 지문의 처리를 빠지고 나서 실시하도록(듯이)
　　　상기의 변경에 수반해, 오늘의 방침(애널/벌/하드)의 개소는 만족 보의 유무로 지문이 변화하도록(듯이)
　　　오늘의 방침 파생을 TFLAG:오늘의 방침으로부터 POLICY("오늘")로 변경
TRAIN_PROCESS.ERB
　　1. 전회의 행동을 표시해 이번 행동을 결정의 개소에서 %TSTR:2%를 %TSTR:전조교 지령%
　　　%TSTR:1%를 %TSTR:조교 지령%에 각각 변경
ACT_ABLE.ERB
　　1. 성 봉계 ACT(ACT_ABLE95~103)에 있어서 TEQUIP:삼각 목마를 규제
COMABLE.ERB
　　1@COMABLE40에 있어서 역강간을 거부 할 수 없도록
그 외
　　본체 부속의 이벤트 구상 번호. txt로부터 존재하고 있지 않는(14, 커맨드 서두) 부분을 삭제

※이것까지 릴리스 한 만큼은 Rel3에 통합되어 있습니다.
  부속의 각 폴더를 본체의 ERB 폴더에 덧쓰기해 사용해 주세요

●연락처
Twitter:@L7switch
mail:layer7.inc@gmail.com

(2013/06/15) /L