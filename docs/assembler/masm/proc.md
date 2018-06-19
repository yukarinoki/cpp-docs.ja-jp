---
title: PROC |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 48eb872d394c3b131d32d4b41c5923883ff36cee
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057774"
---
# <a name="proc"></a>PROC
呼ばれるプロシージャ ブロックの開始と終了をマーク*ラベル*です。 ブロック内のステートメントを呼び出すことができます、**呼び出す**命令または[INVOKE](../../assembler/masm/invoke.md)ディレクティブです。  
  
## <a name="syntax"></a>構文  
  
```  
  
   label PROC [[distance]] [[langtype]] [[visibility]] [[<prologuearg>]]   
[[USES reglist]] [[, parameter [[:tag]]]]...  
[FRAME [:ehandler-address] ]  
statements  
label ENDP  
```  
  
## <a name="remarks"></a>コメント  
 [フレーム [:*ehandler アドレス*] のみ ml64.exe で有効であり、.pdata で関数のテーブルのエントリを生成し、関数の構造化の .xdata 内の情報をアンワインドする MASM 例外処理のアンワインド動作します。  
  
 ときに、**フレーム**属性は、使用、その後である必要があります、[です。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブです。  
  
 参照してください[x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) ml64.exe の使用に関する詳細。  
  
## <a name="example"></a>例  
  
```  
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
  
 上記のコードは次の関数表を生成し、アンワインド情報。  
  
```  
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
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)