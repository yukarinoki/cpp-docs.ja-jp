---
title: PROC |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- PROC
dev_langs:
- C++
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ee26e181f0f40126c86a36889c43405f0b40f5e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680847"
---
# <a name="proc"></a>PROC

呼ばれるプロシージャのブロックの開始と終了をマーク*ラベル*します。 ブロック内のステートメントを呼び出すことができます、**呼び出す**命令または[INVOKE](../../assembler/masm/invoke.md)ディレクティブ。

## <a name="syntax"></a>構文

> *ラベル*PROC [*距離*] [*langtype*] [*可視性*] [\<*prologuearg*>] [使用して*reglist*] [、*パラメーター* [:*タグ*]].<br/>
> [フレーム [:*ehandler アドレス*]]<br/>
> *ステートメント*<br/>
> *ラベル*ENDP

## <a name="remarks"></a>Remarks

[フレーム [:*ehandler アドレス*]] は ml64.exe でのみ有効と MASM .pdata で関数のテーブルのエントリを生成し、関数の構造化の .xdata 内の情報をアンワインドすると、例外処理のアンワインド動作します。

ときに、**フレーム**属性は、使用が続く必要がありますが、[します。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。

参照してください[x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) ml64.exe の使用の詳細についてはします。

## <a name="example"></a>例

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

上記のコードは、次の関数のテーブルを生成し、アンワインド情報。

```Output
FileHeader->Machine 34404
Dumping Unwind Information for file ex2.exe

.pdata entry 1 0x00001000 0x00001023

  Unwind data: 0x00002000

    Unwind version: 1
    Unwind Flags: None
    Size of prologue: 0x08
    Count of codes: 3
    Frame register: rbp
    Frame offset: 0x0
    Unwind codes:

      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00
      Code offset: 0x05, ALLOC_SMALL, size=0x10
      Code offset: 0x01, PUSH_NONVOL, register=rbp
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>