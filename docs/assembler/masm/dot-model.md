---
description: 詳細については、「」を参照してください。モデル (32 ビット MASM)
title: .MODEL
ms.date: 11/05/2019
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: a4324b89f1194227edd7f1d5b7bd70560eca16be
ms.sourcegitcommit: 6183207b11575d7b44ebd7c18918e916a0d8c63d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "97951421"
---
# <a name="model-32-bit-masm"></a>.モデル (32 ビット MASM)

プログラム メモリ モデルを初期化します。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> **.モデル***メモリ-model* ⟦__、__ *language type*⟧⟦__、__ *stack option*⟧

### <a name="parameters"></a>パラメーター

*メモリ-モデル*\
コードとデータ ポインターのサイズを決定する必須パラメーターです。

*言語の種類*\
プロシージャとパブリック シンボルの呼び出しと名前付けの規則を設定する省略可能なパラメーターです。

*stack-オプション*\
省略可能なパラメーター。

*stack オプション* は *、メモリモデル* が **フラット** な場合は使用されません。

**NEARSTACK** を指定すると、スタックセグメントがデータと共に1つの物理セグメント (**dgroup**) にグループ化されます。 スタックセグメントレジスタ (**SS**) は、データセグメントレジスタ (**DS**) と同じアドレスを保持することを前提としています。 **FARSTACK** はスタックを **dgroup** でグループ化しません。そのため、 **SS** は **DS** とは等しくありません。

## <a name="remarks"></a>解説

**.モデル** は、 [x64 (ml64.exe) の MASM](masm-for-x64-ml64-exe.md)では使用されません。

次の表は、16 ビットおよび 32 ビットのプラットフォームを対象とする場合に各パラメーターで使用できる値を示しています。

|パラメーター|32 ビットの値|16 ビットの値 (以前の 16 ビット開発のサポート)|
|---------------|--------------------|----------------------------------------------------------------|
|*メモリ-モデル*|**現状**|**極小**、 **小**、 **コンパクト**、 **中**、 **大**、 **特大**、 **フラット**|
|*言語の種類*|**C**、 **STDCALL**|**C**、 **BASIC**、 **FORTRAN**、 **PASCAL**、 **SYSCALL**、 **STDCALL**|
|*stack-オプション*|使用されていない|**NEARSTACK**、 **FARSTACK**|

## <a name="code"></a>コード

MASM 関連のサンプルについては、[Visual Studio 2010 向けの Visual C++ サンプルと関連ドキュメント](https://github.com/Microsoft/vcsamples)からコンパイラのサンプルをダウンロードしてください。

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

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)
