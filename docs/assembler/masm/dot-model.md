---
title: .MODEL
ms.date: 08/30/2018
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: c409bf10a2f863c380cda6b4822583ffb3787da6
ms.sourcegitcommit: 61121faf879cc581a4d39e4baccabf7cf1f673a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934090"
---
# <a name="model"></a>.MODEL

プログラム メモリ モデルを初期化します。

## <a name="syntax"></a>構文

> .MODEL memorymodel [[, langtype]] [[, stackoption]]

### <a name="parameters"></a>パラメーター

*memorymodel*<br/>
コードとデータ ポインターのサイズを決定する必須パラメーターです。

*langtype*<br/>
プロシージャとパブリック シンボルの呼び出しと名前付けの規則を設定する省略可能なパラメーターです。

*stackoption*<br/>
省略可能なパラメーターです。

*memorymodel* が `FLAT` である場合は *stackoption* は使用されません。

`NEARSTACK` を指定すると、スタック セグメントがデータと共に 1 つの物理セグメント (`DGROUP`) にグループ化されます。 スタック セグメント レジスタ (`SS`) では、データ セグメント レジスタ (`DS`) と同じアドレスを保持することが想定されます。 `FARSTACK` は `DGROUP` でスタックをグループ化しないため、`SS` と `DS` は同じではありません。

## <a name="remarks"></a>解説

.`MODEL` は [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) では使用されません。

次の表は、16 ビットおよび 32 ビットのプラットフォームを対象とする場合に各パラメーターで使用できる値を示しています。

|パラメーター|32 ビットの値|16 ビットの値 (以前の 16 ビット開発のサポート)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`、 `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|未使用|`NEARSTACK`、 `FARSTACK`|

## <a name="code"></a>コード

MASM 関連のサンプルについては、[Visual Studio 2010 向けの Visual C++ サンプルと関連ドキュメント](https://go.microsoft.com/fwlink/p/?linkid=178749)からコンパイラのサンプルをダウンロードしてください。

`.MODEL` ディレクティブの使用例を次に示します。

## <a name="example"></a>例

```asm
; file simple.asm
; For x86 (32-bit), assemble with debug information:
;   ml -c -Zi simple.asm
; For x64 (64-bit), assemble with debug information:
;   ml64 -c -DX64 -Zi simple.asm
;
; In this sample, the 'X64' define excludes source not used
;  when targeting the x64 architecture

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
