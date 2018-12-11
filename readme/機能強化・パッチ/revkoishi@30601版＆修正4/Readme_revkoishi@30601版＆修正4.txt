revkoishi 작업분 for eratohoReverse# 와_L30601판＆수정 4 ver. 1(14/06/07)
※『eratohoReverse# 와_L30601판』에 『eratohoReverse# 와_L30601 수정 4』를 적용한 환경이 대상이 됩니다
※뽑지 않고 인시던트 대응 중점


변경 내용
·질내사정 턴보다 전에 페니스가 빠졌을 경우에서도 뽑지 않고 플래그를 접히도록(듯이) 처리 변경
·W역강간/골짜기를 건너감시에 조교자에게 질내사정했을 때에도 뽑지 않고 판정을 유효하게
·뽑지 않고의 2발/뽑지 않고의 세발이@MARK_CHECK_SOURCE_SURRENDER로 올바르게 판정 할 수 있도록(듯이) 지연 판정용 함수를 추가


뽑지 않고의 n발의 주된 사양 변경 개소
·V⇔A의 체위 변경이나 콤비 네이션 성교 봉사로 분명하게 페니스가 빠져 있는 경우는 뽑지 않고 카운트가 리셋트 되게 되었습니다
·뽑지 않고 지연 판정용 함수 추가에 의해, 뽑지 않고의 2발/뽑지 않고의 세발의 판정 타이밍이 조금 뒤로(다른 대부분 같은 타이밍에) 되었습니다


변경 개소
------------------------------------------------------------------------------------------------------------------------
\ERB\TRAIN\ACT\
	ACT_APPLY.ERB				@ACTION_APPLY_95				A→V 꽂아 바꾸고 때에 TFLAG:뽑지 않고를 꺾는 처리를 추가@v1
								@ACTION_APPLY_96				A→V 꽂아 바꾸고 때에 TFLAG:뽑지 않고를 꺾는 처리를 추가@v1
								@ACTION_APPLY_97				A→V 꽂아 바꾸고 때에 TFLAG:뽑지 않고를 꺾는 처리를 추가@v1
								@ACTION_APPLY_98				A→V 꽂아 바꾸고 때에 TFLAG:뽑지 않고를 꺾는 처리를 추가@v1
								@ACTION_APPLY_99				V→A 꽂아 바꾸고 때에 TFLAG:뽑지 않고를 꺾는 처리를 추가@v1
								@ACTION_APPLY_103				A→V 꽂아 바꾸고 때에 TFLAG:뽑지 않고를 꺾는 처리를 추가@v1

\ERB\TRAIN\ASSI_ACT\
	ASSI_ACT.ERB				@ASSIACT_SELECT					W역강간/골짜기를 건너감시에 TFLAG:뽑지 않고를 꺾는 처리를 추가@v1

\ERB\TRAIN\TRAINSYS\
	SOURCE_1. ERB				@CALC_SOURCE00_EX				미조정@v1
								@CALC_SOURCE00_EX_R				조금 개조@v1
								@IS_UNEXTRACTION				신규 작성. 뽑지 않고 지연 판정용@v1
								@_UNEXTRACTION					신규 작성. 뽑지 않고 지연 판정용@v1
	SOURCE_MARK.ERB				@MARK_CHECK_SOURCE_SURRENDER	뽑지 않고의 2발/뽑지 않고의 세발의 조정@v1
