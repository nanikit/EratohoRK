revkoishi 작업분 for eratohoReverse# 와_L0503+중간 ver. 4(14/05/28)
※R#와_L0503+중간. 7z 로부터의 차분이 됩니다. 변경 개소의 v3+v4는 포함합니다만 v1, v2는 포함하지 않습니다
※v2까지의 변경점은 하부에 기재한 곳 실제 길다고 평판이었으므로 결단적으로 머지 했습니다. 실제 보기 쉽지만 너무 짧아지지 않은 생각도 든다
※R#의 유저 인터페이스의 불평은 나에게 말할 수 있는(떨리는 소리)  인가, 써라고 위협해진 것입니다… 쓰지 않으면 정체를 뿔뿔이 흩어지게 한다고…(강간눈)
※나, 이것이 끝나면, 또 당분간 방랑하면서 구상 쓰려고 생각한다…(수수께끼)


사과와 정정
·revkoishi@0503 test판 v2에서 각인 포인트 표시의 계산이 올바르게 행해지지 않았던 문제를 수정했습니다.
  덧붙여 담당자는 자주적으로 구별 했으므로, 둘러싸 봉으로 두드렸습니다. 안심 주세요
·revkoishi@0503 test판 v2에서 독심술이 변경 가능했던 불편이 올바르게 수정되어 있지 않았기 때문에 수정했습니다.
  덧붙여 담당자는 아바시리에 연수에 보내졌으므로 안심 주세요
·revkoishi@0503+중간 v3에서 TRAIN_PROCESS.ERB의 변경 이력의 갱신 누락이라고 하는 인시던트가 발생했으므로 수정했습니다.
  덧붙여 담당자는 허락해 주세요 부탁합니다 뭐든지 하기 때문이라고 말했으므로, 구별 했습니다. 안심 주세요
·revkoishi@0503+중간 v3에서@GET_SURRENDER_NUM의 반환값 사양의 기재 미스라고 하는 인시던트가 발생했으므로 수정했습니다.
  덧붙여 담당자는 카로우시이기 때문에 구별은 없습니다. 안심 주세요


변경 내용
·@ASSISWAP로, 불필요한 MASTER-ASSI간의 SWAP를 해 PALAM등의 데이터가 파괴되는 불편을 수정
·@CONFIG_ANIMATION_EFFECT를 부르면 REDRAW의 값이 강제적으로 0에 써 교체되는 경우가 있는 것을 수정
·@CONFIGURE로 직접치를 쳐박으면 상황에 관련되지 않고 독심술이 변경 가능했던 불편을 수정
·@CONFIG_PAD로 Enter 키를 새롭게 할당하는 것이 할 수 없었던 불편을 수정
·일부 환경에서 페이드 처리가 잘 되지 않았던 것 같은 것으로 대책
·스테이터스 표시 화면과 마력 사용 화면, 콘피그 화면을 으득으득 개악. 주로 표시 항목과 색과 확장성(표시 관련의 미비 수정 포함한다)
·굴복 실적 관련의 결단적 대규모 손질. 질내 사정 V절정을【굴복:60】으로서 부활. 타 2종 추가
·물총 관련의 사양 추가(보완). EX:MASTER:물총이 기능하도록(듯이), EXP:물총 경험의 추가,【굴복:59】물총의 추가
·화면에 표시되는 c/v/b/a는 대문자에 수정
·범용 함수를 몇개인가 추가
·그 외미조정


스테이터스 화면의 주된 사양
·쓸데없게 버튼화해지고 있던 개소를 버튼화하지 않도록 했습니다. 안심입니다
·아라이먼트의 색을 조정했으므로, 안심 주세요
·능력, 경험중 0의 것은 회색 표시로 했습니다. 안심입니다
·분류 칼라 표시와 조교 이력의 개행 위치 자동 판별로 대응했습니다. 안심 주세요


마력 사양 화면의 주된 사양
·조교 도구 분류표시 위에, 커스터마이즈 후 명칭 변경＆무지개색표시합니다. 안심 주세요
·소질 변동 칼라 표시로 개행 위치 자동 판별. 많은 날도 안심입니다


콘피그 화면의 주된 사양
·ON/OFF의 집합 화면은 기본적으로 체크 박스를 표시. 알기 쉬움 중점에 의해 안심입니다


굴복 실적의 주된 사양
·Str.csv로 Lv와 대상 성별과 표시 문언 2종을 일괄 정의 가능.
  문언 재검토 시에 grep 결과와 노려보기 할 필요는 없어졌으므로 안심 주세요. Lv변경도 용이해 안심입니다
  (기존의 세이브 데이터는 재계산하지 않으면 어긋남이 발생합니다만 대응도 용이하므로 안심 주세요)
·스테이터스 화면에서는 정의되고 있는 분만큼 Lv 마다 번호순서에 표시합니다.
  Str.csv로 Lv 순서에 정의할 필요는 없기 때문에 안심 주세요. 개행 위치도 자동 판정. 안심입니다
·CSTR:구상 독자 실적 X로, 구상 독자적인 실적을 정의 가능 얏타! 최대 16 범위 사용할 수 있기 때문에 안심 주세요.
  판정은@KOJO_CHECK_SURRENDER_KX1내인가, 구상내의 임의의 위치에서@MARK_CHECK_GET를 사용할 수 있습니다. 안심입니다
·본체의 굴복 실적이 64종→112종까지 늘릴 수 있게 되었습니다. 안심입니다
·신규 실적은 물총, 질내 사정 V절정, 사중 절정, 젖은 것 4종입니다. 여자 아이도 후타나리의 아이도 안심 주세요


변경 개소
------------------------------------------------------------------------------------------------------------------------
\CSV\
    Cflag.csv                   302, 각인 2                       신규 추가@v3
    Cstr.csv                    70-85                           신규 추가@v3
    Exp.csv                     14, 물총 경험                   신규 추가@v3
    Str.csv                     1300-1427                       굴복 실적의 사양 변경과 신규 추가@v4
                                                                ※문언안은/L=산으로부터 받았습니다. 감사합니다
    Strname.csv                 1300-1427                       신규 추가@v4

\ERB\FUNCTION\GETTER\
    COMMON_GETTER_CHARA.ERB     @ABL_TYPE                       신규 작성@v3
                                @EXP_TYPE                       신규 작성@v3
                                @TALENT_TYPE                    미조정@v1
    COMMON_GETTER_SITUATION.ERB @GET_ITEMNAME                   신규 작성@v2
                                @ITEM_TYPE                      R#사양으로 변경@v1
                                @ITEM_TYPENAME                  R#사양으로 변경@v1
    COMMON_GETTER_SURRENDER.ERB @GET_SURRENDER_LV               신규 작성@v3
                                @GET_SURRENDER_NUM              신규 작성@v3
                                @GET_SURRENDER_POINT            신규 작성@v3
                                @GET_SURRENDER_STR_M            신규 작성@v3
                                @GET_SURRENDER_STR_T            신규 작성@v3
                                @IS_SURRENDER_DISPLAYABLE       신규 작성@v4
                                @SURRENDER_LV2POINT             신규 작성@v3

ERB\FUNCTION\PROCESS\
    COMMON_PROCESS_CALC.ERB     @ASSISWAP                       불필요한 SWAP에 의해 불편이 생기고 있었으므로 수정@v1

ERB\FUNCTION\PROCESS\KOMEIJI_FUNCTIONS\
    MISC.ERB                    @INPUT_RANGE                    모패치보다 수중에 넣어@v1
                                @NOBYNAME                       모구상보다 수중에 넣어@v1
                                @SIGNS                          모패치보다 수중에 넣어@v1
                                @SIGNV                          모패치보다 수중에 넣어@v1
                                @SRL                            모구상보다 수중에 넣어@v1

\ERB\FUNCTION\에 째─실마리응\
    PANIMATION.ERB              @FADE                           일부 환경(주로 나의 NotePC)로 페이드가 잘 기능하지 않았기 때문에 대책@v4

ERB\SYSTEM\
    START_SELECT.ERB            @START_CHARA_SELECT_T           미조정@v2

\ERB\SYSTEM\SHOP\
    BONUS_GAIN.ERB              @BONUS_GAIN                     R#사양으로 변경. LOCAL 지옥을 구별. 미조정@v3
    CONFIGURE.ERB               @CONFIGURE                      상황에 관련되지 않고 독심술이 변경 가능했어를 수정. 외, 미조정@v3
                                @CONFIG_AI_FREEDOM              미조정@2
                                @CONFIG_ANIMATION_EFFECT        REDRAW를 바꾼 채로 되돌리지 않은 것을 수정. 그리고 약간마개조@v1
                                @CONFIG_MASTER_PREGNACY         @CONFIGURE에 통합@v3
                                @CONFIG_MINDREADING             @CONFIGURE에 통합@v3
                                @CONFIG_PAD                     Enter를 새롭게 할당하는 것이 할 수 없었던 것을 수정. 외, 미조정@v3
                                @CONFIG_RENAME_MASTER           미조정@v2
                                @CONFIG_SHOW_TALENT             @CONFIGURE에 통합@v2
                                @KOJO_COUFIG_SET                @KOJO_CONFIG_SET로 이름 변경. 미조정@v3
                                @SET_KEY_DEFAULT                미조정@v2
    SHOP_TRAINERDATA.ERB        @NEW_PRINT_ABL                  개행 위치와 표시 항목과 색의 조정@v3
                                @NEW_PRINT_EXP                  참조 차이를 수정. 개행 위치와 표시 항목과 색의 조정@v3
                                @NEW_PRINT_TALENT               개행 위치등 조정. LOCAL 지옥을 구별. 미조정@v3
                                @PRINT_STATUS                   미조정@v2
                                @PRINT_STATUS2                  미취득분도 회색 표시되도록(듯이) 변경. 개행 위치등 조정. 굴복 실적의 사양 변경@v4
                                @PRINT_TENSION                  미조정@v2

\ERB\TRAIN\
    EVENTCOMEND.ERB             @EVENTCOMEND                    굴복 실적의 사양 변경@v3
    TRAIN_PROCESS.ERB           @SHOW_STATUS                    쓸데없게 버튼화하지 않게 변경. 미조정@v4
    USERCOM.ERB                 @SHOW_EQUIP                     물총 추가, c절정/v절정/b절정/a절정을 대문자에 수정. 외, 미조정@v3

\ERB\TRAIN\ACT\
    ACT_MESSAGE.ERB             @TRAIN_MESSAGE2_90              +가 되지 않는 경우도 있던 것 같았으므로 수정@v3
                                @TRAIN_MESSAGE2_91              전술(아마 여기는 안 되지만)@v3
                                @TRAIN_MESSAGE2_92              전술(아마 여기는 안 되지만)@v3

\ERB\TRAIN\TRAINSYS\
    EXP_CHECK.ERB               @EXP_CHECK                      굴복 실적의 사양 변경. c경험/v경험/b경험을 대문자에 수정. 물총 추가@v3
    INFO_GAUGE.ERB              @INFO_GAUGE_TRAINER             쓸데없게 버튼화하지 않게 변경. 외, 미조정@v3
    SOURCE_1. ERB                @CALC_SOURCE00_EX               뽑지 않고의 2발이라고 뽑지 못하고의 세발을 조정. 물총 추가@v3
    SOURCE_MARK.ERB             @MARK_CHECK_GET                 굴복 실적의 사양 변경@v3
                                @MARK_CHECK_SOURCE_SURRENDER    굴복 실적의 사양 변경. 뽑지 않고의 2발/세발을 SOURCE_1. ERB@CALC_SOURCE00_EX에 이동@v4
                                                                ※TFLAG:뽑지 않고가 이 직후에 클리어 되기 (위해)때문에. 혹은 부실
                                @MARK_CHECK_SOURCE_SURRENDER_CHECK  굴복 실적의 사양 변경@v3
