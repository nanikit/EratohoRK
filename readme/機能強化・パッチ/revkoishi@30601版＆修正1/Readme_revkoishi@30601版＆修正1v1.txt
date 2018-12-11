revkoishi 작업분 for eratohoReverse# 와_L30601판＆수정 1 ver. 1(14/06/01)
※『eratohoReverse# 와_L30601판』에 『eratohoReverse# 와_L30601 수정 1』를 적용한 환경이 대상이 됩니다
※전임자의 인시던트 대응 중점인. 전임자는 세프크 했으므로 안심 주세요


변경 내용
·조교 대상이 여자 아이의 경우, 스테이터스 화면에서【아누스에 삽입 시켰다】가 표시되지 않는 문제를 수정  ※페니스 밴드 사용으로 취득 가능
·【아누스에 삽입 시켰다】의 취득시의 문언이 올바르게 표시되지 않고【】가 되는 문제를 수정  ※『,』가 들어가 있었다
·STRNAME:1305로 STRNAME:1306이 거꾸로 되고 있었으므로 수정  ※세이브 데이터에는 영향 없을 것…
·코멘트의 잘못을 수정. 그 외미조정


변경 개소
------------------------------------------------------------------------------------------------------------------------
\CSV\
    Str.csv                     1305, 1 A___아누스를         코멘트의 잘못을 수정(쾌B→쾌A)
                                1306, 1 A___가슴을             코멘트의 잘못을 수정(쾌A→쾌B)
                                1347, 3 P___아누스에         여자 아이의 경우에 스테이터스 화면에서 표시되지 않는 문제를 수정. 취득시 문언이 표시되지 않는 문제를 수정
    Strname.csv                 1305, 쾌B                   쾌B→쾌A에 수정
                                1306, 쾌A                   쾌A→쾌B에 수정
                                                            ※이 2개소는 캐릭터 라인에 의한 참조를 하고 있지 않기 때문에 세이브 데이터에 영향 없습니다. 안심 주세요

\ERB\FUNCTION\GETTER\
    COMMON_GETTER_SURRENDER.ERB @IS_SURRENDER_DISPLAYABLE   다른 판정에도 사용할 수 있도록(듯이) 명칭을@IS_SURRENDER_ENABLE로 변경

\ERB\SYSTEM\SHOP\
    SHOP_TRAINERDATA.ERB        @PRINT_STATUS2              @IS_SURRENDER_DISPLAYABLE의 함수명 변경에 수반하는 수정

\ERB\TRAIN\TRAINSYS\
    SOURCE_MARK.ERB             @MARK_CHECK_GET             만일을 위해@IS_SURRENDER_ENABLE로 유효 판정을 실시하도록(듯이) 변경
