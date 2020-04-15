---
title: ARM64 組み込み
description: Microsoft C++ コンパイラでサポートされている ARM64 の組み込みの一覧。
f1_keywords:
- __break
- __addx18byte
- __addx18word
- __addx18dword
- __addx18qword
- __cas8
- __cas16
- __cas32
- __cas64
- __casa8
- __casa16
- __casa32
- __casa64
- __casl8
- __casl16
- __casl32
- __casl64
- __casal8
- __casal16
- __casal32
- __casal64
- __crc32b
- __crc32h
- __crc32w
- __crc32d
- __crc32cb
- __crc32ch
- __crc32cw
- __crc32cd
- __getReg
- __getRegFp
- __getCallerReg
- __getCallerRegFp
- __hlt
- __incx18byte
- __incx18word
- __incx18dword
- __incx18qword
- __ldar8
- __ldar16
- __ldar32
- __ldar64
- __ldapr8
- __ldapr16
- __ldapr32
- __ldapr64
- __prefetch2
- __readx18byte
- __readx18word
- __readx18dword
- __readx18qword
- __setReg
- __setRegFp
- __setCallerReg
- __setCallerRegFp
- __stlr8
- __stlr16
- __stlr32
- __stlr64
- __swp8
- __swp16
- __swp32
- __swp64
- __swpa8
- __swpa16
- __swpa32
- __swpa64
- __swpl8
- __swpl16
- __swpl32
- __swpl64
- __swpal8
- __swpal16
- __swpal32
- __swpal64
- __sys
- __svc
- __writex18byte
- __writex18word
- __writex18dword
- __writex18qword
author: sigatrev
ms.author: magardn
ms.date: 11/14/2019
ms.openlocfilehash: 196518439445824ddf5a7a841b30eb816251ba60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368215"
---
# <a name="arm64-intrinsics"></a>ARM64 組み込み

マイクロソフト C++ コンパイラ (MSVC) は、ARM64 アーキテクチャで次の組み込みが使用可能になります。 ARM の詳細については[、ARM 開発者ドキュメント](https://developer.arm.com/docs)Web サイトのアーキテクチャとソフトウェア開発ツールのセクションを参照してください。

## <a name="neon"></a><a name="top"></a>ネオン

ARM64 の NEON ベクトル命令セット拡張は、単一命令複数データ (SIMD) 機能を提供します。 これらは、x86 および x64 アーキテクチャ プロセッサに共通する MMX および SSE ベクトル命令セットに似ています。

NEON 組み込みは、ヘッダー ファイル*arm64_neon.h*で提供されているとおりにサポートされています。 NEON 組み込み用の MSVC サポートは、ARM インフォセンター Web サイトの[ARM NEON 組み込みリファレンス](https://static.docs.arm.com/ihi0073/c/IHI0073C_arm_neon_intrinsics_ref.pdf)に記載されている ARM64 コンパイラのサポートに似ています。

## <a name="arm64-specific-intrinsics-listing"></a><a name="A"></a>ARM64 固有の組み込みリスト

|関数名|命令|関数プロトタイプ|
|-------------------|-----------------|------------------------|
|__break|Brk|ボイド__break(int)|
|__addx18byte||void __addx18byte (符号なし長、符号なし文字)|
|__addx18word||void __addx18word (符号なし長、符号なしショート)|
|__addx18dword||void __addx18dword(符号なし長、符号なし長)|
|__addx18qword||void __addx18qword (符号なし長、符号なし__int64)|
|__cas8|CASB|未署名__int8 __cas8 (未署名__int8揮発性* _Target、符号なし__int8_Comp、未署名__int8_Value)|
|__cas16|現金|未署名__int16 __cas16 (未署名__int16揮発性* _Target、符号なし__int16_Comp、符号なし__int16_Value)|
|__cas32|CAS|未署名__int32 __cas32 (未署名__int32揮発性* _Target、未署名__int32_Comp、符号なし__int32_Value)|
|__cas64|CAS|未署名の__int64 __cas64 (未署名__int64揮発性* _Target、未署名の__int64_Comp、未署名の__int64_Value)|
|__casa8|CASAB|符号なし__int8 __casa8 (未署名__int8揮発性* _Target、未署名__int8_Comp、未署名__int8_Value)|
|__casa16|カサ|未署名の__int16 __casa16 (未署名__int16揮発性* _Target、符号なし__int16_Comp、未署名の__int16_Value)|
|__casa32|カサ|未署名__int32 __casa32 (未署名__int32揮発性* _Target、符号なし__int32_Comp、未署名の__int32_Value)|
|__casa64|カサ|未署名__int64 __casa64 (未署名__int64揮発性* _Target、符号なし__int64_Comp、未署名__int64_Value)|
|__casl8|カスポンド|未署名の__int8__casl8 (未署名__int8揮発性* _Target、未署名の__int8_Comp、未署名の__int8_Value)|
|__casl16|カスル|符号なし__int16 __casl16 (未署名__int16揮発性* _Target、符号なし__int16_Comp、未署名__int16_Value)|
|__casl32|Casl|符号なし__int32 __casl32(未署名__int32揮発性* _Target、未署名__int32_Comp、未署名__int32_Value)|
|__casl64|Casl|符号なし__int64 __casl64(未署名__int64揮発性* _Target、符号なし__int64_Comp、符号なし__int64_Value)|
|__casal8|カサルブ|符号なし__int8__casal8(未署名__int8揮発性* _Target、未署名の__int8_Comp、未署名__int8_Value)|
|__casal16|カサル|未署名__int16 __casal16 (未署名__int16揮発性* _Target、符号なし__int16_Comp、未署名__int16_Value)|
|__casal32|カザール|未署名__int32__casal32 (未署名__int32揮発性* _Target、符号なし__int32_Comp、符号なし__int32_Value)|
|__casal64|カザール|未署名__int64 __casal64 (未署名__int64揮発性* _Target、未署名__int64_Comp、未署名__int64_Value)|
|__crc32b|CRC32B|未署名__int32__crc32b(未署名__int32、署名されていない__int32)|
|__crc32h|CRC32H|署名されていない__int32__crc32h(未署名の__int32、署名されていない__int32)|
|__crc32w|CRC32W|署名されていない__int32__crc32w(未署名__int32、署名されていない__int32)|
|__crc32d|CRC32X|未署名__int32 __crc32d (未署名__int32、署名されていない__int64)|
|__crc32cb|CRC32CB|署名されていない__int32__crc32cb(未署名の__int32、署名されていない__int32)|
|__crc32ch|CRC32CH|署名されていない__int32 __crc32ch (未署名__int32、署名されていない__int32)|
|__crc32cw|CRC32CW|署名されていない__int32__crc32cw(署名されていない__int32、署名されていない__int32)|
|__crc32cd|CRC32CX|署名されていない__int32__crc32cd(未署名の__int32、署名されていない__int64)|
|__dmb|DMB|void __dmb(unsigned int `_Type`)<br /><br /> 命令ストリームにメモリ バリア操作を挿入します。 パラメーター `_Type` で、バリアによって適用される制限の種類を指定します。<br /><br /> 適用できる制限の種類の詳細については、「[メモリ バリアの制限](#BarrierRestrictions)」を参照してください。|
|__dsb|DSB|void __dsb(unsigned int _Type)<br /><br /> 命令ストリームにメモリ バリア操作を挿入します。 パラメーター `_Type` で、バリアによって適用される制限の種類を指定します。<br /><br /> 適用できる制限の種類の詳細については、「[メモリ バリアの制限](#BarrierRestrictions)」を参照してください。|
|__isb|ISB|void __isb(unsigned int _Type)<br /><br /> 命令ストリームにメモリ バリア操作を挿入します。 パラメーター `_Type` で、バリアによって適用される制限の種類を指定します。<br /><br /> 適用できる制限の種類の詳細については、「[メモリ バリアの制限](#BarrierRestrictions)」を参照してください。|
|__getReg||符号なし__int64__getReg(int)|
|__getRegFp||ダブル__getRegFp(int)|
|__getCallerReg||符号なし__int64__getCallerReg(int)|
|__getCallerRegFp||ダブル__getCallerRegFp(int)|
|__hvc|HVC|unsigned int __hvc(unsigned int, ...)|
|__hlt|HLT|int __hlt (符号なし int,.)|
|__incx18byte||無効__incx18byte(符号なし長)|
|__incx18word||void __incx18word(符号なし長)|
|__incx18dword||無効__incx18dword(符号なし長)|
|__incx18qword||void __incx18qword(符号なし長)|
|__iso_volatile_load16||__int16_iso_volatile_load16(\_定数揮発性\__int16) \*<br /><br /> 詳細については、「 [__iso_volatile_load/ストアの組み込み](#IsoVolatileLoadStore)」を参照してください。|
|__iso_volatile_load32||__int32 \__iso_volatile_load32(定数\_揮発性\*_int32)<br /><br /> 詳細については、「 [__iso_volatile_load/ストアの組み込み](#IsoVolatileLoadStore)」を参照してください。|
|__iso_volatile_load64||__int64 \__iso_volatile_load64(恒\_常\*性揮発性_int64)<br /><br /> 詳細については、「 [__iso_volatile_load/ストアの組み込み](#IsoVolatileLoadStore)」を参照してください。|
|__iso_volatile_load8||__int8 \__iso_volatile_load8(定数\_揮発性\*_int8)<br /><br /> 詳細については、「 [__iso_volatile_load/ストアの組み込み](#IsoVolatileLoadStore)」を参照してください。|
|__iso_volatile_store16||ボイド__iso_volatile_store16(揮発性\__int16 \* \_,_int16)<br /><br /> 詳細については、「 [__iso_volatile_load/ストアの組み込み](#IsoVolatileLoadStore)」を参照してください。|
|__iso_volatile_store32||ボイド__iso_volatile_store32(揮発性\__int32 \* \_、_int32)<br /><br /> 詳細については、「 [__iso_volatile_load/ストアの組み込み](#IsoVolatileLoadStore)」を参照してください。|
|__iso_volatile_store64||ボイド__iso_volatile_store64(揮発性\__int64 \* \_,_int64)<br /><br /> 詳細については、「 [__iso_volatile_load/ストアの組み込み](#IsoVolatileLoadStore)」を参照してください。|
|__iso_volatile_store8||ボイド__iso_volatile_store8(揮発性\__int8 \* \_、_int8)<br /><br /> 詳細については、「 [__iso_volatile_load/ストアの組み込み](#IsoVolatileLoadStore)」を参照してください。|
|__ldar8|LDARB|符号なし__int8 __ldar8 (未署名__int8揮発性* _Target)|
|__ldar16|LDARH|符号なし__int16 __ldar16 (未署名__int16揮発性* _Target)|
|__ldar32|LDAR|符号なし__int32 __ldar32 (未署名__int32揮発性* _Target)|
|__ldar64|LDAR|符号なし__int64 __ldar64 (未署名__int64揮発性* _Target)|
|__ldapr8|LDAPRB|符号なし__int8 __ldapr8 (未署名__int8揮発性* _Target)|
|__ldapr16|LDAPRH|符号なし__int16 __ldapr16 (未署名__int16揮発性* _Target)|
|__ldapr32|LDAPR|符号なし__int32 __ldapr32 (未署名__int32揮発性* _Target)|
|__ldapr64|LDAPR|符号なし__int64 __ldapr64(未署名__int64揮発性* _Target)|
|__mulh||\__int64__mulh(_int64、_int64)\_ \_|
|__prefetch|PRFM|void \___cdecl _prefetch \*(const void )<br /><br /> 指定した`PRFM`アドレスまたはその近くのメモリにすぐに`PLDL1KEEP`アクセスできるプリフェッチ操作をシステムに提供します。 システムによっては、実行時のパフォーマンスを向上させるために、そのメモリへのアクセス パターンを最適化する場合があります。 ただし、C++ 言語側からすると、この関数には目に見える効果がなく、何も実行しないことがあります。|
|__prefetch2|PRFM|void \___cdecl _prefetch(const void \*, uint8_t prfop)<br /><br /> 指定された`PRFM`プリフェッチ操作を使用して、指定したアドレスまたはその近くのメモリにすぐにアクセスできるメモリ ヒントを提供します。 システムによっては、実行時のパフォーマンスを向上させるために、そのメモリへのアクセス パターンを最適化する場合があります。 ただし、C++ 言語側からすると、この関数には目に見える効果がなく、何も実行しないことがあります。|
|__readx18byte||符号なし文字__readx18byte(符号なし長)|
|__readx18word||符号なしの短__readx18word(符号なし長)|
|__readx18dword||符号なし長__readx18dword(符号なし長)|
|__readx18qword||未署名の__int64 __readx18qword (符号なし長)|
|__setReg||void __setReg(int、未署名の__int64)|
|__setRegFp||ボイド__setRegFp(int、ダブル)|
|__setCallerReg||ボイド__setCallerReg(int、未署名の__int64)|
|__setCallerRegFp||ボイド__setCallerRegFp(int、ダブル)|
|__sev|SEV|void __sev(void)|
|__static_assert||void __static_assert (int, \*const char )|
|__stlr8|STLRB|void __stlr8(未署名__int8揮発性* _Target、符号なし__int8_Value)|
|__stlr16|STLRH|void __stlr16(未署名__int16揮発性*_Target、符号なし__int16_Value)|
|__stlr32|STLR|void __stlr32(未署名__int32揮発性* _Target、未署名__int32_Value)|
|__stlr64|STLR|void __stlr64(未署名__int64揮発性* _Target、未署名__int64_Value)|
|__swp8|SWPB|未署名__int8 __swp8(未署名__int8揮発性* _Target、符号なし__int8_Value)|
|__swp16|SWPH|未署名__int16 __swp16 (未署名__int16揮発性* _Target、未署名__int16 _Value)|
|__swp32|SWP|未署名__int32__swp32(未署名__int32揮発性* _Target、未署名__int32_Value)|
|__swp64|SWP|符号なし__int64 __swp64(未署名__int64揮発性* _Target、符号なし__int64_Value)|
|__swpa8|SWPAB|符号なし__int8__swpa8(未署名__int8揮発性* _Target、符号なし__int8_Value)|
|__swpa16|スピア|未署名の__int16 __swpa16(未署名__int16揮発性* _Target、符号なし__int16_Value)|
|__swpa32|SWPA|未署名__int32 __swpa32(未署名__int32揮発性* _Target、符号なし__int32_Value)|
|__swpa64|SWPA|未署名__int64__swpa64(未署名__int64揮発性* _Target、未署名__int64_Value)|
|__swpl8|SWPLB|未署名__int8 __swpl8(未署名__int8揮発性* _Target、符号なし__int8_Value)|
|__swpl16|SWPLH|未署名の__int16 __swpl16 (未署名__int16揮発性* _Target、未署名__int16_Value)|
|__swpl32|SWPL|符号なし__int32 __swpl32(未署名__int32揮発性* _Target、符号なし__int32_Value)|
|__swpl64|SWPL|未署名__int64 __swpl64(未署名__int64揮発性* _Target、未署名__int64_Value)|
|__swpal8|SWPALB|未署名の__int8 __swpal8 (未署名__int8揮発性* _Target、未署名__int8_Value)|
|__swpal16|スウェーパル|符号なし__int16 __swpal16 (未署名__int16揮発性* _Target、符号なし__int16_Value)|
|__swpal32|スウォーパル|符号なし__int32 __swpal32(未署名__int32揮発性* _Target、符号なし__int32_Value)|
|__swpal64|スウォーパル|符号なし__int64 __swpal64(未署名__int64揮発性* _Target、未署名__int64_Value)|
|__sys|SYS|符号なしの int __sys(int, __int64)|
|__svc|SVC|符号なし int __svc (符号なし int,.)|
|__wfe|WFE|void __wfe(void)|
|__wfi|WFI|void __wfi(void)|
|__writex18byte||void __writex18byte (符号なし長、符号なし文字)|
|__writex18word||void __writex18word (符号なし長、符号なしショート)|
|__writex18dword||void __writex18dword(符号なし長、符号なし長)|
|__writex18qword||void __writex18qword (符号なし長、符号なし__int64)|
|__umulh||署名\_されていない_int64__umulh(未署名\__int64、署名\_されていない_int64)|
|_CopyDoubleFromInt64||ダブル_CopyDoubleFromInt64(_int64)\_|
|_CopyFloatFromInt32||フロート_CopyFloatFromInt32(_int32)\_|
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat(float)|
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble(double)|
|_CountLeadingOnes||unsigned int _CountLeadingOnes(unsigned long)|
|_CountLeadingOnes64||符号なしの int _CountLeadingOnes64 \_(署名されていない_int64)|
|_CountLeadingSigns||unsigned int _CountLeadingSigns(long)|
|_CountLeadingSigns64||符号なし _CountLeadingSigns64(\__int64)|
|_CountLeadingZeros||unsigned int _CountLeadingZeros(unsigned long)|
|_CountLeadingZeros64||符号なし int _CountLeadingZeros64 \_(署名されていない_int64)|
|_ReadStatusReg|MRS|\__int64_ReadStatusReg(int)|
|_WriteStatusReg|MSR|ボイド_WriteStatusReg(int,_int64) \_|

[[ トップに戻る](#top)]

### <a name="memory-barrier-restrictions"></a><a name="BarrierRestrictions"></a>メモリ バリアの制限

組み込`__dmb`み関数 (データ`__dsb`メモリ バリア)、(データ同期バリア)、および`__isb`(命令同期バリア) は、次の定義済みの値を使用して、共有ドメインの観点からメモリ バリアの制限と、操作の影響を受けるアクセスの種類を指定します。

|制限値|説明|
|-----------------------|-----------------|
|_ARM64_BARRIER_SY|システム全体、読み取りと書き込み。|
|_ARM64_BARRIER_ST|システム全体、書き込みのみ。|
|_ARM64_BARRIER_LD|フルシステム、読み取り専用。|
|_ARM64_BARRIER_ISH|内部共有可能、読み取りと書き込み。|
|_ARM64_BARRIER_ISHST|内部共有可能、書き込みのみ。|
|_ARM64_BARRIER_ISHLD|内部共有可能、読み取り専用。|
|_ARM64_BARRIER_NSH|共有不可、読み取りと書き込み。|
|_ARM64_BARRIER_NSHST|共有不可、書き込みのみ。|
|_ARM64_BARRIER_NSHLD|共有不可能、読み取り専用。|
|_ARM64_BARRIER_OSH|外部共有可能、読み取りと書き込み。|
|_ARM64_BARRIER_OSHST|外部共有可能、書き込みのみ。|
|_ARM64_BARRIER_OSHLD|外部共有可能、読み取り専用。|

組み`__isb`込みでは、現在有効な制限は_ARM64_BARRIER_SYだけです。その他の値はすべてアーキテクチャによって予約されています。

### <a name="__iso_volatile_loadstore-intrinsics"></a><a name="IsoVolatileLoadStore"></a>__iso_volatile_load/ストア組み込み

これらの組み込み関数は、コンパイラの最適化の対象とならない読み込みと格納を明示的に実行します。

```C
__int16 __iso_volatile_load16(const volatile __int16 * Location);
__int32 __iso_volatile_load32(const volatile __int32 * Location);
__int64 __iso_volatile_load64(const volatile __int64 * Location);
__int8 __iso_volatile_load8(const volatile __int8 * Location);

void __iso_volatile_store16(volatile __int16 * Location, __int16 Value);
void __iso_volatile_store32(volatile __int32 * Location, __int32 Value);
void __iso_volatile_store64(volatile __int64 * Location, __int64 Value);
void __iso_volatile_store8(volatile __int8 * Location, __int8 Value);
```

#### <a name="parameters"></a>パラメーター

*場所*\
読み取る、または書き込むメモリ位置のアドレスです。

*値*\
指定したメモリ位置に書き込む値 (固有の値のみを格納)。

#### <a name="return-value-load-intrinsics-only"></a>戻り値 (組み込み値の読み込みのみ)

Location*で指定*されたメモリ位置の値。

#### <a name="remarks"></a>解説

`__iso_volatile_load8/16/32/64`組み込みと`__iso_volatile_store8/16/32/64`組み込み関数を使用すると、コンパイラの最適化の対象ではないメモリ アクセスを明示的に実行できます。 コンパイラは、これらの操作の相対的な順序を削除、合成、または変更することはできません。 ただし、暗黙のハードウェア メモリ バリアは生成されません。 したがって、ハードウェアでも複数のスレッド間で観察可能なメモリ アクセスの順序が変更される場合があります。 より正確には、これらの組み込みは **、/volatile:iso**でコンパイルされた次の式と同じです。

```cpp
int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;
```

組み込みは、volatile 変数を格納する volatile ポインターを受け取ることに注意してください。 ただし、引数として揮発性のポインターを使用する必要はありません。 これらの操作のセマンティクスは、通常の非揮発性型を使用する場合とまったく同じです。

**/volatile:iso**コマンド ライン引数の詳細については[、「/volatile (volatile キーワード解釈)」](../build/reference/volatile-volatile-keyword-interpretation.md)を参照してください。

## <a name="arm64-support-for-intrinsics-from-other-architectures"></a><a name="I"></a>他のアーキテクチャの組み込み用 ARM64 のサポート

次の表は、ARM64 プラットフォームでサポートされている他のアーキテクチャの組み込みについて示しています。 ARM64 の組み込みの動作が他のハードウェア アーキテクチャでの動作と異なる場合は、追加の詳細が記載されています。

|関数名|関数プロトタイプ|
|-------------------|------------------------|
|__assume|void __assume(int)|
|__code_seg|void __code_seg(const \*char)|
|__debugbreak|ボイド__cdecl_debugbreak(\_ボイド)|
|__fastfail|__declspec(noreturn)\_無効_fastfail (符号なし int)|
|__nop|void __nop(void)|
|__yield|void __yield(void)**注:** ARM64 プラットフォームでは、この関数は YIELD 命令を生成します。 この命令は、スレッドが、プログラムに悪影響を及ぼすことなく、一時的に実行を中断するタスク (スピンロックなど) を実行していることを示します。 これにより、CPU は、他の場合は無駄になる可能性のある実行サイクル中に他のタスクを実行できます。|
|_AddressOfReturnAddress|ボイド\*_AddressOfReturnAddress(ボイド)|
|_BitScanForward|符号なし char _BitScanForward(符号\*なし長_Index、符号なし長_Mask)|
|_BitScanForward64|符号なし char _BitScanForward64(符号\*なし長_Index、符号なし__int64_Mask)|
|_BitScanReverse|符号なし文字_BitScanReverse(符号なし長\*_Index、符号なし長_Mask)|
|_BitScanReverse64|符号なし char _BitScanReverse64 (\*符号なし長_Index、未署名__int64_Mask)|
|_bittest|符号なし文字_bittest(長い\*定数、長い)|
|_bittest64|符号なし文字_bittest64(__int64 \*const ,__int64)|
|_bittestandcomplement|符号なし文字_bittestandcomplement(長\*い、 長い)|
|_bittestandcomplement64|符号なし文字_bittestandcomplement64(__int64 \*、__int64)|
|_bittestandreset|符号なし文字_bittestandreset(長\*い、 長い)|
|_bittestandreset64|符号なし文字_bittestandreset64(__int64 \*、__int64)|
|_bittestandset|符号なし文字_bittestandset(長\*い、 長い)|
|_bittestandset64|符号なし文字_bittestandset64(__int64 \*、__int64)|
|_byteswap_uint64|未署名の\___int64_cdecl_byteswap_uint64 (\_署名されていない_int64)|
|_byteswap_ulong|unsigned long __cdecl _byteswap_ulong(unsigned long)|
|_byteswap_ushort|unsigned short __cdecl _byteswap_ushort(unsigned short)|
|_disable|void __cdecl _disable(void)**注:** ARM64 プラットフォームでは、この`MSR DAIFCLR,#2`関数は命令を生成します。組み込みとしてのみ利用できます。|
|_enable|void __cdecl _enable (void)**注:** ARM64 プラットフォームでは、`MSR DAIFSET,#2`この関数は命令を生成します。組み込みとしてのみ利用できます。|
|_lrotl|unsigned long __cdecl _lrotl(unsigned long, int)|
|_lrotr|unsigned long __cdecl _lrotr(unsigned long, int)|
|_ReadBarrier|void _ReadBarrier(void)|
|_ReadWriteBarrier|void _ReadWriteBarrier(void)|
|_ReturnAddress|ボイド\*_ReturnAddress(ボイド)|
|_rotl|unsigned int __cdecl _rotl(unsigned int _Value, int _Shift)|
|_rotl16|unsigned short _rotl16(unsigned short _Value, unsigned char _Shift)|
|_rotl64|未署名の\___int64_cdecl_rotl64(署名\_されていない_int64_Value、int _Shift)|
|_rotl8|unsigned char _rotl8(unsigned char _Value, unsigned char _Shift)|
|_rotr|unsigned int __cdecl _rotr(unsigned int _Value, int _Shift)|
|_rotr16|unsigned short _rotr16(unsigned short _Value, unsigned char _Shift)|
|_rotr64|符号なし__int64_cdecl_rotr64(\_未署名\__int64_Value、int _Shift)|
|_rotr8|unsigned char _rotr8(unsigned char _Value, unsigned char _Shift)|
|_setjmpex|int __cdecl _setjmpex(jmp_buf)|
|_WriteBarrier|void _WriteBarrier(void)|

[[ トップに戻る](#top)]

## <a name="interlocked-intrinsics"></a>インターロック組み込み

インタロックされた組み込みは、アトミックな読み取り/変更/書き込み操作を実行するときに使用する一連の組み込みです。 一部の組み込みは、すべてのプラットフォームに共通です。 多数の人がいるので、ここには別々に記載されています。 定義はほとんど冗長なので、一般的な用語で考える方が簡単です。 組み込みの名前から、その具体的な動作を推測できます。

次の表は、非ビットテストインターロック組み込みの ARM64 サポートをまとめたものです。 テーブル内の各セルで、行の一番左のセルにある操作名と、列の一番上にある型名を `_Interlocked` の最後に付け加えると、組み込みの名前になります。 たとえば、行と`Xor``8`列の交差部分のセルは、完全にサポートされているの`_InterlockedXor8`に対応しています。 サポートされているほとんどの関数には、オプションのサフィックス `_acq`、`_rel`、および `_nf` が用意されています。 `_acq` サフィックスは "取得" のセマンティクスを示し、`_rel` サフィックスは "解放" のセマンティクスを示します。 「`_nf`フェンスなし」の接尾辞は ARM および ARM64 に固有で、次のセクションで説明します。

||8|16|32|64|128|P|
|-|-------|--------|--------|--------|-------|-------|
|追加|なし|なし|[完全]|[完全]|なし|なし|
|And|[完全]|[完全]|[完全]|[完全]|なし|なし|
|CompareExchange|[完全]|[完全]|[完全]|[完全]|[完全]|[完全]|
|Decrement|なし|[完全]|[完全]|[完全]|なし|なし|
|Exchange|[完全]|[完全]|[完全]|[完全]|なし|[完全]|
|ExchangeAdd|[完全]|[完全]|[完全]|[完全]|なし|なし|
|Increment|なし|[完全]|[完全]|[完全]|なし|なし|
|Or|[完全]|[完全]|[完全]|[完全]|なし|なし|
|Xor|[完全]|[完全]|[完全]|[完全]|なし|なし|

キー:

- **完全**: プレーン`_acq`、 `_rel`、 `_nf` 、および フォームをサポートします。

- **なし**: サポートされていません

### <a name="_nf-no-fence-suffix"></a><a name="nf_suffix"></a>_nf (フェンスなし) 接尾部

"no fence" サフィックスは`_nf`、他の 3 つの形式 (プレーン、、`_acq`および`_rel`) とは対照的に、操作がメモリ バリアとして動作しないことを示します。 フォームの`_nf`使用の 1 つとして、複数のスレッドによって同時に更新されるが、複数のスレッドの実行中に値が使用されない統計カウンターを維持することが考えられます。

### <a name="list-of-interlocked-intrinsics"></a>インタロック組み込みリスト

|関数名|関数プロトタイプ|
|-------------------|------------------------|
|_InterlockedAdd|長い_InterlockedAdd(長\*い_volatile 、長い)|
|_InterlockedAdd64|__int64_InterlockedAdd64(_int64\_揮発性\* \_、_int64)|
|_InterlockedAdd64_acq|__int64_InterlockedAdd64_acq(_int64\_揮発性\*、_int64) \_|
|_InterlockedAdd64_nf|__int64_InterlockedAdd64_nf(\_揮発性_int64 \* \_、_int64)|
|_InterlockedAdd64_rel|__int64_InterlockedAdd64_rel(\_揮発性\*_int64、_int64) \_|
|_InterlockedAdd_acq|長い_InterlockedAdd_acq(長\*揮発性、長い)|
|_InterlockedAdd_nf|長い_InterlockedAdd_nf(長\*揮発性、長い)|
|_InterlockedAdd_rel|長い_InterlockedAdd_rel(長\*揮発性、長)|
|_InterlockedAnd|ロング_InterlockedAnd(長揮発性\*、長)|
|_InterlockedAnd16|ショート_InterlockedAnd16(ショート揮発性\*、ショート)|
|_InterlockedAnd16_acq|ショート_InterlockedAnd16_acq(ショート揮発性\*、ショート)|
|_InterlockedAnd16_nf|ショート_InterlockedAnd16_nf(ショート揮発性\*、ショート)|
|_InterlockedAnd16_rel|ショート_InterlockedAnd16_rel(ショート揮発性\*、ショート)|
|_InterlockedAnd64|__int64_InterlockedAnd64(_int64\_揮発性\* \_、_int64)|
|_InterlockedAnd64_acq|__int64_InterlockedAnd64_acq(_int64\_揮発性\* \_、_int64)|
|_InterlockedAnd64_nf|__int64_InterlockedAnd64_nf(_int64\_揮発性\* \_、_int64)|
|_InterlockedAnd64_rel|__int64_InterlockedAnd64_rel(_int64\_揮発性\*、_int64) \_|
|_InterlockedAnd8|char _InterlockedAnd8(char\*揮発性、char)|
|_InterlockedAnd8_acq|char _InterlockedAnd8_acq(char\*揮発性、char)|
|_InterlockedAnd8_nf|文字_InterlockedAnd8_nf(char\*揮発性、char)|
|_InterlockedAnd8_rel|char _InterlockedAnd8_rel(char\*揮発性、char)|
|_InterlockedAnd_acq|長い_InterlockedAnd_acq(長\*揮発性、長)|
|_InterlockedAnd_nf|長い_InterlockedAnd_nf(長\*揮発性、長い)|
|_InterlockedAnd_rel|長い_InterlockedAnd_rel(長\*揮発性、長)|
|_InterlockedCompareExchange|長__cdecl_InterlockedCompareExchange(長揮発性\*、長い、長い)|
|_InterlockedCompareExchange_acq|長い_InterlockedCompareExchange_acq(長\*い揮発性、長い、長い)|
|_InterlockedCompareExchange_nf|長い_InterlockedCompareExchange_nf(長\*揮発性、長い、長い)|
|_InterlockedCompareExchange_rel|長い_InterlockedCompareExchange_rel(長\*い揮発性、長い、長い)|
|_InterlockedCompareExchange16|短い_InterlockedCompareExchange16(短\*い揮発性 、短い、短い)|
|_InterlockedCompareExchange16_acq|短い_InterlockedCompareExchange16_acq(短\*い揮発性 、短い、短い)|
|_InterlockedCompareExchange16_nf|ショート_InterlockedCompareExchange16_nf(短揮発性\*、 ショート、 ショート)|
|_InterlockedCompareExchange16_rel|ショート_InterlockedCompareExchange16_rel(短揮発性\*、ショート、ショート)|
|_InterlockedCompareExchange64|__int64_InterlockedCompareExchange64(\_揮発性\*_int64、_int64、_int64) \_ \_|
|_InterlockedCompareExchange64_acq|__int64_InterlockedCompareExchange64_acq(\_揮発性\*_int64、_int64、_int64) \_ \_|
|_InterlockedCompareExchange64_nf|__int64_InterlockedCompareExchange64_nf(_int64\_揮発性\*、_int64、_int64) \_ \_|
|_InterlockedCompareExchange64_rel|__int64_InterlockedCompareExchange64_rel(\_揮発性\*_int64 \_、_int64、_int64) \_|
|_InterlockedCompareExchange8|文字_InterlockedCompareExchange8(char \*volatile 、char、char)|
|_InterlockedCompareExchange8_acq|char _InterlockedCompareExchange8_acq(char \*volatile 、char、char)|
|_InterlockedCompareExchange8_nf|char _InterlockedCompareExchange8_nf(char\*揮発性、文字、文字)|
|_InterlockedCompareExchange8_rel|char _InterlockedCompareExchange8_rel(char \*volatile 、char、char)|
|_InterlockedCompareExchangePointer|ボイド\*_InterlockedCompareExchangePointer(ボイド\*揮発性\*、\*ボイド\*、ボイド)|
|_InterlockedCompareExchangePointer_acq|ボイド\*_InterlockedCompareExchangePointer_acq(ボイド\*揮発性\*、\*ボイド\*、 ボイド )|
|_InterlockedCompareExchangePointer_nf|ボイド\*_InterlockedCompareExchangePointer_nf(ボイド\*揮発性\*、\*ボイド\*、 ボイド )|
|_InterlockedCompareExchangePointer_rel|ボイド\*_InterlockedCompareExchangePointer_rel(ボイド\*揮発性\*、\*ボイド\*、ボイド)|
|_InterlockedCompareExchange128|符号なしの char\_ \* _InterlockedCompareExchange128(\_揮発性\__int64_Destination、_ExchangeHigh_int64、_int64 _ExchangeLow、_int64 \_ \* _ComparandResult)|
|_InterlockedCompareExchange128_acq|符号なし文字_InterlockedCompareExchange128_acq(\_揮発性\*_Destination、_int64_ExchangeHigh、_int64_ExchangeLow、_int64_ComparandResult_int64) \_ \_ \_ \*|
|_InterlockedCompareExchange128_nf|符号なし char\__InterlockedCompareExchange128_nf(\*揮発性\__Destination_int64、 \__int64 \__ExchangeHigh、_int64 _ExchangeLow、_int64 _ComparandResult) \*|
|_InterlockedCompareExchange128_rel|符号なし文字_InterlockedCompareExchange128_rel(\_揮発性\*_Destination、_int64_ExchangeHigh、_int64_ExchangeLow、_int64_ComparandResult) \_ \_ \_ \* _int64)|
|_InterlockedDecrement|長い__cdecl_InterlockedDecrement(長\*揮発性)|
|_InterlockedDecrement16|ショート_InterlockedDecrement16(ショート揮発性\*)|
|_InterlockedDecrement16_acq|ショート_InterlockedDecrement16_acq(ショート揮発性\*)|
|_InterlockedDecrement16_nf|ショート_InterlockedDecrement16_nf(ショート揮発性\*)|
|_InterlockedDecrement16_rel|ショート_InterlockedDecrement16_rel(ショート揮発性\*)|
|_InterlockedDecrement64|__int64_InterlockedDecrement64(_int64\_揮発性\*)|
|_InterlockedDecrement64_acq|__int64_InterlockedDecrement64_acq(_int64\_揮発性\*)|
|_InterlockedDecrement64_nf|__int64_InterlockedDecrement64_nf(_int64\_揮発性\*)|
|_InterlockedDecrement64_rel|__int64_InterlockedDecrement64_rel(_int64\_揮発性\*)|
|_InterlockedDecrement_acq|ロング_InterlockedDecrement_acq(長揮発性\*)|
|_InterlockedDecrement_nf|ロング_InterlockedDecrement_nf(長揮発性\*)|
|_InterlockedDecrement_rel|ロング_InterlockedDecrement_rel(長揮発性\*)|
|_InterlockedExchange|長い__cdecl_InterlockedExchange(長\*揮発性_Target、長い)|
|_InterlockedExchange_acq|長い_InterlockedExchange_acq(長\*揮発性_Target、長い)|
|_InterlockedExchange_nf|長い_InterlockedExchange_nf(長\*揮発性_Target、長い)|
|_InterlockedExchange_rel|ロング_InterlockedExchange_rel(長揮発性\*_Target、長)|
|_InterlockedExchange16|ショート_InterlockedExchange16(短い\*揮発性_Target、ショート)|
|_InterlockedExchange16_acq|ショート_InterlockedExchange16_acq(短い\*揮発性_Target、ショート)|
|_InterlockedExchange16_nf|ショート_InterlockedExchange16_nf(短い\*揮発性_Target、ショート)|
|_InterlockedExchange16_rel|ショート_InterlockedExchange16_rel(短い\*揮発性_Target、ショート)|
|_InterlockedExchange64|__int64_InterlockedExchange64(_int64\_揮発性\*_Target、_int64) \_|
|_InterlockedExchange64_acq|__int64_InterlockedExchange64_acq(\_揮発性\*_Target_int64_int64) \_|
|_InterlockedExchange64_nf|__int64_InterlockedExchange64_nf(_int64\_揮発性\*_Target、_int64) \_|
|_InterlockedExchange64_rel|__int64_InterlockedExchange64_rel(_int64\_揮発性\*_Target、_int64) \_|
|_InterlockedExchange8|char _InterlockedExchange8(char\*揮発性_Target、char)|
|_InterlockedExchange8_acq|char _InterlockedExchange8_acq(char\*揮発性_Target、char)|
|_InterlockedExchange8_nf|char _InterlockedExchange8_nf(char\*揮発性_Target、char)|
|_InterlockedExchange8_rel|char _InterlockedExchange8_rel(char\*揮発性_Target、char)|
|_InterlockedExchangeAdd|長い__cdecl_InterlockedExchangeAdd(長\*揮発性、長)|
|_InterlockedExchangeAdd16|ショート_InterlockedExchangeAdd16(ショート揮発性\*、ショート)|
|_InterlockedExchangeAdd16_acq|ショート_InterlockedExchangeAdd16_acq(ショート揮発性\*、ショート)|
|_InterlockedExchangeAdd16_nf|ショート_InterlockedExchangeAdd16_nf(ショート揮発性\*、ショート)|
|_InterlockedExchangeAdd16_rel|ショート_InterlockedExchangeAdd16_rel(ショート揮発性\*、ショート)|
|_InterlockedExchangeAdd64|__int64_InterlockedExchangeAdd64(_int64\_揮発性\* \_、_int64)|
|_InterlockedExchangeAdd64_acq|__int64_InterlockedExchangeAdd64_acq(\_揮発性\*_int64、_int64) \_|
|_InterlockedExchangeAdd64_nf|__int64_InterlockedExchangeAdd64_nf(_int64\_揮発性\* \_、_int64)|
|_InterlockedExchangeAdd64_rel|__int64_InterlockedExchangeAdd64_rel(_int64\_揮発性\* \_、_int64)|
|_InterlockedExchangeAdd8|文字_InterlockedExchangeAdd8(char \*volatile 、char)|
|_InterlockedExchangeAdd8_acq|char _InterlockedExchangeAdd8_acq(char \*volatile 、char)|
|_InterlockedExchangeAdd8_nf|char _InterlockedExchangeAdd8_nf(char \*volatile 、char)|
|_InterlockedExchangeAdd8_rel|char _InterlockedExchangeAdd8_rel(char \*volatile 、char)|
|_InterlockedExchangeAdd_acq|長い_InterlockedExchangeAdd_acq(長\*揮発性、長い)|
|_InterlockedExchangeAdd_nf|長い_InterlockedExchangeAdd_nf(長\*揮発性、長)|
|_InterlockedExchangeAdd_rel|長い_InterlockedExchangeAdd_rel(長\*揮発性、長い)|
|_InterlockedExchangePointer|ボイド\*_InterlockedExchangePointer(ボイド\*揮発性\*_Target、ボイド\*)|
|_InterlockedExchangePointer_acq|ボイド\*_InterlockedExchangePointer_acq(揮発性\*\*_Targetボイド、ボイド\*)|
|_InterlockedExchangePointer_nf|ボイド\*_InterlockedExchangePointer_nf(ボイド\*揮発性\*_Target、ボイド\*)|
|_InterlockedExchangePointer_rel|ボイド\*_InterlockedExchangePointer_rel(ボイド\*揮発性\*_Target、ボイド\*)|
|_InterlockedIncrement|長い__cdecl_InterlockedIncrement(長\*揮発性)|
|_InterlockedIncrement16|短い_InterlockedIncrement16(短\*揮発性)|
|_InterlockedIncrement16_acq|ショート_InterlockedIncrement16_acq(短揮発性\*)|
|_InterlockedIncrement16_nf|ショート_InterlockedIncrement16_nf(ショート揮発性\*)|
|_InterlockedIncrement16_rel|ショート_InterlockedIncrement16_rel(ショート揮発性\*)|
|_InterlockedIncrement64|__int64_InterlockedIncrement64(_int64\_揮発性\*)|
|_InterlockedIncrement64_acq|__int64_InterlockedIncrement64_acq(_int64\_揮発性\*)|
|_InterlockedIncrement64_nf|__int64_InterlockedIncrement64_nf(_int64\_揮発性\*)|
|_InterlockedIncrement64_rel|__int64_InterlockedIncrement64_rel(_int64\_揮発性\*)|
|_InterlockedIncrement_acq|ロング_InterlockedIncrement_acq(長揮発性\*)|
|_InterlockedIncrement_nf|ロング_InterlockedIncrement_nf(長揮発性\*)|
|_InterlockedIncrement_rel|ロング_InterlockedIncrement_rel(長揮発性\*)|
|_InterlockedOr|長い_InterlockedOr(長\*揮発性、長)|
|_InterlockedOr16|ショート_InterlockedOr16(短揮発性\*、ショート)|
|_InterlockedOr16_acq|ショート_InterlockedOr16_acq(ショート揮発性\*、ショート)|
|_InterlockedOr16_nf|短い_InterlockedOr16_nf(短\*い揮発性、短い)|
|_InterlockedOr16_rel|ショート_InterlockedOr16_rel(短揮発性\*、ショート)|
|_InterlockedOr64|__int64_InterlockedOr64(\_揮発性_int64 \* \_、_int64)|
|_InterlockedOr64_acq|__int64_InterlockedOr64_acq(\_揮発性\*_int64、_int64) \_|
|_InterlockedOr64_nf|__int64_InterlockedOr64_nf(\_揮発性\*_int64_int64) \_|
|_InterlockedOr64_rel|__int64_InterlockedOr64_rel(\_揮発性\*_int64、_int64) \_|
|_InterlockedOr8|char _InterlockedOr8(char \*volatile 、char)|
|_InterlockedOr8_acq|文字_InterlockedOr8_acq(char \*volatile 、char)|
|_InterlockedOr8_nf|文字_InterlockedOr8_nf(char\*揮発性、char)|
|_InterlockedOr8_rel|char _InterlockedOr8_rel(チャ\*ル揮発性、char)|
|_InterlockedOr_acq|長い_InterlockedOr_acq(長\*揮発性、長い)|
|_InterlockedOr_nf|長い_InterlockedOr_nf(長\*揮発性、長)|
|_InterlockedOr_rel|長い_InterlockedOr_rel(長\*揮発性、長い)|
|_InterlockedXor|ロング_InterlockedXor(長揮発性\*、ロング)|
|_InterlockedXor16|短い_InterlockedXor16(短\*い揮発性、短い)|
|_InterlockedXor16_acq|ショート_InterlockedXor16_acq(ショート揮発性\*、ショート)|
|_InterlockedXor16_nf|ショート_InterlockedXor16_nf(ショート揮発性\*、ショート)|
|_InterlockedXor16_rel|ショート_InterlockedXor16_rel(短揮発性\*、ショート)|
|_InterlockedXor64|__int64_InterlockedXor64(_int64\_揮発性\*、_int64) \_|
|_InterlockedXor64_acq|__int64_InterlockedXor64_acq(_int64\_揮発性\*、_int64) \_|
|_InterlockedXor64_nf|__int64_InterlockedXor64_nf(_int64\_揮発性\* \_、_int64)|
|_InterlockedXor64_rel|__int64_InterlockedXor64_rel(_int64\_揮発性\* \_、_int64)|
|_InterlockedXor8|文字_InterlockedXor8(char\*揮発性、char)|
|_InterlockedXor8_acq|文字_InterlockedXor8_acq(char\*揮発性、文字)|
|_InterlockedXor8_nf|char _InterlockedXor8_nf(char \*volatile 、char)|
|_InterlockedXor8_rel|文字_InterlockedXor8_rel(char\*揮発性、文字)|
|_InterlockedXor_acq|長い_InterlockedXor_acq(長\*揮発性、長い)|
|_InterlockedXor_nf|長い_InterlockedXor_nf(長\*揮発性、長い)|
|_InterlockedXor_rel|長い_InterlockedXor_rel(長\*揮発性、長い)|

[[ トップに戻る](#top)]

### <a name="_interlockedbittest-intrinsics"></a>_interlockedbittest組み込み

プレーンインターロックビットテスト組み込みは、すべてのプラットフォームに共通です。 ARM64`_acq`では`_rel`、 `_nf` 、 、およびバリアントが追加され、この資料の前半の[「_nf (フェンスなし) サフィックス](#nf_suffix)」で説明したように、操作のバリアセマンティクスを変更するだけです。

|関数名|関数プロトタイプ|
|-------------------|------------------------|
|_interlockedbittestandreset|符号なし char _interlockedbittestandreset(\*長揮発性、長)|
|_interlockedbittestandreset_acq|符号なし char _interlockedbittestandreset_acq(\*長揮発性 、長い)|
|_interlockedbittestandreset_nf|符号なし char _interlockedbittestandreset_nf(\*長揮発性、長)|
|_interlockedbittestandreset_rel|符号なし文字_interlockedbittestandreset_rel(長揮発性\*、長)|
|_interlockedbittestandreset64|符号なし char _interlockedbittestandreset64(\*揮発性__int64 、__int64)|
|_interlockedbittestandreset64_acq|符号なし char _interlockedbittestandreset64_acq(\*揮発性__int64 、__int64)|
|_interlockedbittestandreset64_nf|符号なし char _interlockedbittestandreset64_nf(\*揮発性__int64 、__int64)|
|_interlockedbittestandreset64_rel|符号なし char _interlockedbittestandreset64_rel(\*揮発性__int64 、__int64)|
|_interlockedbittestandset|符号なし char _interlockedbittestandset(\*長揮発性 、長)|
|_interlockedbittestandset_acq|符号なし char _interlockedbittestandset_acq(\*長揮発性、長)|
|_interlockedbittestandset_nf|符号なし char _interlockedbittestandset_nf(\*長揮発性、長)|
|_interlockedbittestandset_rel|符号なし char _interlockedbittestandset_rel(\*長揮発性、長)|
|_interlockedbittestandset64|符号なし char _interlockedbittestandset64(__int64揮発性\*、__int64)|
|_interlockedbittestandset64_acq|符号なし char _interlockedbittestandset64_acq(__int64揮発性\*、__int64)|
|_interlockedbittestandset64_nf|符号なし char _interlockedbittestandset64_nf(\*揮発性__int64 、__int64)|
|_interlockedbittestandset64_rel|符号なしの文字_interlockedbittestandset64_rel(揮発性\*__int64 、__int64)|

[[ トップに戻る](#top)]

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)\
[ARM 組み込み](arm-intrinsics.md)\
[ARM アセンブラ参照](../assembler/arm/arm-assembler-reference.md)\
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)
