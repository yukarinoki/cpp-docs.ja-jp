---
title: .MODEL
ms.date: 08/30/2018
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: 5c7d5a1cfe16ef3cb1d79617133cd1ceccdfb78c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633511"
---
# <a name="model"></a>.MODEL

プログラムのメモリ モデルを初期化します。

## <a name="syntax"></a>構文

> .モデルの memorymodel [, langtype] [、stackoption]

### <a name="parameters"></a>パラメーター

*memorymodel*<br/>
コードとデータのポインターのサイズを決定する必須パラメーターです。

*langtype*<br/>
プロシージャとパブリック シンボルの呼び出し元と名前付け規則を設定する省略可能なパラメーター。

*stackoption*<br/>
省略可能なパラメーターです。

*stackoption*場合は使用されません*memorymodel*は`FLAT`します。

指定する`NEARSTACK`スタック セグメントを 1 つの物理セグメントにグループ化 (`DGROUP`) のデータと共にします。 スタック セグメント レジスタ (`SS`) がデータ セグメントの登録と同じアドレスを保持するために使用されます (`DS`)。 `FARSTACK` スタックにはグループ化されません`DGROUP`ため`SS`と等しくない`DS`します。

## <a name="remarks"></a>Remarks

.`MODEL` 使用されていない[x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)します。

次の表は、16 ビットおよび 32 ビットのプラットフォームを対象とする場合に、各パラメーターの値を示します。

|パラメーター|32 ビット値|16 ビット値 (以前の 16 ビットの開発のサポート)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|未使用|`NEARSTACK`, `FARSTACK`|

## <a name="code"></a>コード

MASM 関連のサンプルでは、コンパイラ、サンプルのダウンロード[Visual C のサンプルおよび関連ドキュメントを Visual Studio 2010 の](http://go.microsoft.com/fwlink/p/?linkid=178749)します。

次の例では、使用、`.MODEL`ディレクティブ。

## <a name="example"></a>例

```asm
; file simple.asm
; For x86 (32-bit), assemble with debug information:
;   ml -c -Zi simple.asm
; For x64 (64-bit), assemble with debug information:
;   ml64 -c -DX64 -Zi simple.asm
;
; In this sample, the 'X64' define excludes source not used
;  when targeting the x64 architecture

ifndef X64
.686p
.XMM
.model flat, C
endif

.data
; user data

.code
; user code

fxn PROC public
  xor eax, eax ; zero function return value
  ret
fxn ENDP

end
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>

