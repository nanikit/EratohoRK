2012/10/1

이하의 불편을 수정

·SANDBOX, EXTRA 모드 개시시에 조교 대상의 체력 기력 이성의 최대치가 이상해지는 일이 있다
·밀어 넘어뜨리기중에 조교 대상이 절정 해도 해방되지 않는다
·조교로 얻을 수 있는 마력이 상정보다 적다

2012/9/26

자기 부담 수정이 류는 기타노p
이하의 불편을 수정

·윤활, 울적이 오르지 않는다
·안면 승마하고 있는데 조교자가 조교 대상의 배후에 있는 것 같은 문장이 표시된다
·조수 1의 행동이 조수 2의 행동으로서 표시되는 일이 있다
·소질 「장신」을 가지고 있어도 표시되지 않는다


구체적인 변경 개소

COMMON_GETTER_CHARA.ERB
·장신의 카테고리를 비표시로부터 체질에 이동

TRAIN_PROCESS.ERB
·조수의 ACT 처리 후에 ASSI = ASSI:1을 추가

MASTER_POSE.ERB
·안면 승마, 밀어 넘어뜨리기에 의한 강제 위로 돌리고의 처리로
  TCVAR:MASTER:위치 전후 = TEQUIP:밀어 넘어뜨리기중 || IS_NOWACTNAME("밀어 넘어뜨린다") ? 1 # 0
  ↓
  TCVAR:MASTER:위치 전후 = 1

SOURCE.ERB
SOURCE_1.ERB
·SUMARRAY가 입력치를 무시해 항상 0을 돌려주어 오는 곳을 단순 가산에 치환

MASTERCUSTOM.ERB
·BASE_MASTER_SETUP의 처리를 복잡화
