_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
·명칭		R#0616 test판++용 마음대로 수정 패치 Rel3
·동작환경	eratohoReverse# 0616 test판++
·작자		/L
·배포원	http://ux.getuploader.com/aba98725/
_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#

[수정 내용]
  □CSV
　　1. CFLAG:1230, 노예의 목걸이 봉인을 추가
　　2. Str.csv, 0~103까지를 ACT 분류마다 단락짓도록(듯이)
　　3. Train.csv, 0~70까지를 분류마다 단락짓도록(듯이)
　　4. Tequip.csv, 88, 착의 노출 100, 조교 대상 C사용에 코멘트를 추가
　　5. Tcvar.csv, 40, 상태 변화의 코멘트를 현행 사양에 맞도록(듯이)
  □ACT_ABLE.ERB
　　1@ACT_ABLE11가슴 애무에 있어서 TEQUIP:성교 봉사중, 2, 5, 6때는 규제하도록(듯이)
  □ACT_APPLY.ERB
　　1@ACTION_APPLY2_57에 있어서 REACT 분류 "거부", "날뛴다", "도망친다"의 개소를 수정
　　　COM 자위하기 시작하면 ACT 파생으로 분리해, 더러운 처리도 분리하도록(듯이)
  □ACT_MESSAGE.ERB
　　1@TRAIN_MESSAGE2_11에 있어서 TFLAG:ACT 파생 == 3만으로 수용 취급의 개소에! IS_COMGRONAME("날뛴다")를 추가
　　2@TRAIN_MESSAGE2_27에 밀어 넘어뜨려 종료의 분기를 추가
　　3@TRAIN_MESSAGE2_42의 IS_COMGRONAME("적극적 따른다")를 IS_COMGRONAME("받아들인다/적극적 따른다")에
　　4@TRAIN_MESSAGE2 봉사계의 거절이 되는 개소에 IS_NOWCOMNAME("자위하기 시작한다")를 추가
　　5@TRAIN_MESSAGE_51에 ACT 파생 1, 페라 강제를 추가
  □SOURCE_MESSAGE.ERB
　　1. 조교 대상 절정 및 조교 대상 사정때, NOWEX:MASTER:방뇨를 연주하도록(듯이)
　　2. 하층에 NOWEX:MASTER:방뇨를 처리하는 개소를 추가
  □COM_XX.ERB
　　1@COM7에 있어서 REACT1를 COM 인상"0으로부터 멀어진다"에
　　2@COM21에 있어서 REACT 파생을 정의해, V/A성교를 각각 REACT 파생으로 참조할 수 있도록(듯이)
　　3@COM30로 REACT 파생을 정의. REACTION_MESSAGE에 모방해, 쾌SOURCE로 파생 0으로 1으로 나눈다
　　4@COM33를@COM7와 같게 수정. 파생 1의 「의견을 내다니 좋은 담력이구나!」는 납득할 수 있는 형태에
　　5@COM52내의 TFLAG:ACT를 IS_NOWACTNAME에. 자위계는 GETBIT로 보도록(듯이) 각각 변경
  □COMABLE.ERB
　　1@COMABLE21 및@COMABLE22에 있어서 TALENT:MASTER:남자인 경우의 규제를 해제
　　2@COMABLE50에 있어서 ACT15, 키스시에 발생하는 것은 위화감이 있었으므로 규제
  □REACTION_MESSAGE.ERB
　　1. COM0에 아이마스크 장착시의 분기를 추가
　　2. COM7에 「의견을 내다니 좋은 담력이구나!」의 경우의 처리를 추가
　　3. COM22, 부하 2의 개소를 V_SEX(TARGET)로 나누도록(듯이)
　　4. COM32에 부하 2의 처리를 추가
　　5. COM33에 「두려움에 대해 초조한다」의 처리를 추가
　　6. COM41에 「소극적인의가 마음에 들지 않는다」의 처리를 추가
  □EVENT_S.ERB
　　1@EVENTTURNEND, 노예의 목걸이 이벤트를 구상측에서 봉인 가능한 것 같게
　　　임의의 개소에서 CFLAG:노예의 목걸이 봉인 = 1하는 것으로 봉인이 가능
  □COMMON_GETTER_TRAIN.ERB
　　1@ACTSTR에 있어서 그 외의 처리가 될 때, ACT 명칭을 돌려주도록(듯이)

[Rel2, 수정 내용]
  □SOURCE.ERB
　　1. KOJO_EVENT(20) 호출 개소의 MASTER_EX 및 TARGET_EX의 비트화에서의 지정을 중지해 생략 하도록(듯이)
　　2. 상기 개소의 앞에 FLAG:지문 제어를 리셋트 하도록(듯이)

[Rel3, 수정 내용]
  □CSV
　　1. Tcvar.csv 60, 만족 보너스/61, 이번에 대만족/62, 오늘의 만족 보너스를 추가
  □EVETRAIN.ERB
　　1. 만족 보너스의 RESULT 참조 개소를 확장 후, TCVAR:오늘의 만족 보너스에의 대입 처리를 추가해 조교중에 참조 가능한 것 같게
　　　해당 플래그는 39행째에-1에 리셋트
  □EVENTCOMEND.ERB
　　1. 대만족 보너스의 개소, 723행째에 TCVAR:이번에 대만족에의 대입 처리를 추가. 현상, 다른 개소에서의 참조에는 이용하지 않았다
  □ACT_ABLE.ERB
　　1@ACT_ABLE35에 있어서 TEQUIP:페니스 밴드, TEQUIP:바이브에 의한 규제를 해제
　　　TEQUIP:애널 바이브, TEQUIP:애널 비즈, TEQUIP:관장기＋플러그때는 규제하도록(듯이)
  □ACT_MESSAGE.ERB
　　1@TRAIN_MESSAGE_25, "클립 로터를 붙이려고 했다"→"클립 로터를 설치하려고 했다"로 변경
　　2@TRAIN_MESSAGE2_35, IS_COMGRONAME("소극적 따른다")의 개소에 있어서, "싫어했다", "비명을 지른다"를 COM로 분리
　　　보다 납득을 할 수 있는 형태로 변경
　　3@TRAIN_MESSAGE2_41, IS_COMGRONAME("허가를 청한다")의 개소를 고쳐 써
  □REACTION_MESSAGE.ERB
　　1. 파생을 TRAINNAME:SELECTCOM로 기술하도록(듯이) 변경
　　2. COM7, 허가를 청하는 것에 있어서, 부하 2의 개소를 일부 수정
　　3. COM8, 기분 좋게 해 TFLAG:REACT 파생 == 1의 처리를 추가

※Emuera1818+v7도 붙여 있습니다. 이번은 필수라고 할 것이 아닙니다만, 가능한 한 새로운 것이 바람직합니다

※부속의 각 폴더를 본체의 ERB, CSV 폴더에 덧쓰기해 사용해 주세요
  현상 어디까지나 비공식인 것을 이해하신 후에, 도입해 주세요
  또, 당패치를 도입한 일에 의한 불편의 서포트를, 시스템 측에 요구하지 않게 부탁합니다

●연락처
Twitter:@L7switch
mail:layer7.inc@gmail.com
(2014/03/26) /L