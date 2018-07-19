---
title: プロローグ/エピローグ コードの記述に関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b7f4e2c25d7ead3399020221c1e0e9633557d24
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942108"
---
# <a name="considerations-for-writing-prologepilog-code"></a>プロローグ コードとエピローグ コードを記述する際の考慮事項
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 独自のプロローグとエピローグのコード シーケンスを記述する前に、スタック フレームがどのように配置されるかを理解することが重要です。_ _Local_size 記号を使用する方法を知っておくと便利です。  
  
##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a> スタック フレームのレイアウト  
 この例は、32 ビット関数で使用される標準プロローグ コードを示しています。  
  
```  
push        ebp                ; Save ebp  
mov         ebp, esp           ; Set stack frame pointer  
sub         esp, localbytes    ; Allocate space for locals  
push        <registers>        ; Save registers  
```  
  
 `localbytes` 変数は、ローカル変数のスタックで必要なバイト数を表します。また、`<registers>` 変数は、スタックに格納されるレジスタの一覧を表すプレースホルダーです。 レジスタをプッシュした後、スタックに他の適切なデータを配置できます。 対応するエピローグ コードは次のとおりです。  
  
```  
pop         <registers>   ; Restore registers  
mov         esp, ebp      ; Restore stack pointer  
pop         ebp           ; Restore ebp  
ret                       ; Return from function  
```  
  
 スタックは、常に下に (上位メモリ アドレスから下位メモリ アドレスに) 向かって大きくなります。 基本ポインター (`ebp`) は、プッシュされた `ebp` の値を指します。 ローカル領域は `ebp-4` で始まります。 ローカル変数にアクセスするには、`ebp` からのオフセットを計算します。そのためには、`ebp` から適切な値を減算します。  
  
##  <a name="_pluslang___local_size"></a> _ _LOCAL_SIZE  
 コンパイラは、関数プロローグ コードのインライン アセンブラー ブロックで使用するための _ _local_size、シンボルを提供します。 カスタム プロローグ コードで、スタック フレームにローカル変数の領域を割り当てるときに、このシンボルを使用します。  
  
 コンパイラは、_ _local_size の値を決定します。 その値は、すべてのユーザー定義のローカル変数とコンパイラにより生成された一時変数の合計バイト数です。 _ _Local_size は、即時のオペランドとしてのみ使用できます。これは、式で使用できません。 このシンボルの値は、変更することも再定義することもできません。 例えば:  
  
```  
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov        eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 カスタムのプロローグおよびエピローグ シーケンスを含む naked 関数の次の例では、プロローグ シーケンスで _ _local_size シンボルを使用します。  
  
```  
// the__local_size_symbol.cpp  
// processor: x86  
__declspec ( naked ) int main() {  
   int i;  
   int j;  
  
   __asm {      /* prolog */  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
   __asm {   /* epilog */  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [naked 関数呼び出し](../cpp/naked-function-calls.md)