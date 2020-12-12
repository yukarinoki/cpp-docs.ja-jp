---
description: '詳細情報: プロローグ/エピローグコードの記述に関する考慮事項'
title: Prolog-Epilog コードの記述に関する考慮事項
ms.date: 11/04/2016
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
ms.openlocfilehash: 6deb6e9120c83992a7fe2529d0c9366b8e191056
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204772"
---
# <a name="considerations-for-writing-prologepilog-code"></a>プロローグ コードとエピローグ コードを記述する際の考慮事項

**Microsoft 固有の仕様**

独自のプロローグとエピローグのコードシーケンスを記述する前に、スタックフレームがどのようにレイアウトされているかを理解することが重要です。また、シンボルの使用方法についても理解しておくと便利です `__LOCAL_SIZE` 。

## <a name="stack-frame-layout"></a><a name="_pluslang_c.2b2b_.stack_frame_layout"></a> スタックフレームのレイアウト

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

## <a name="__local_size"></a><a name="_pluslang___local_size"></a> __LOCAL_SIZE

コンパイラは、 `__LOCAL_SIZE` 関数プロローグコードのインラインアセンブラーブロックで使用するのシンボルを提供します。 カスタム プロローグ コードで、スタック フレームにローカル変数の領域を割り当てるときに、このシンボルを使用します。

の値はコンパイラによって決定され `__LOCAL_SIZE` ます。 その値は、すべてのユーザー定義のローカル変数とコンパイラにより生成された一時変数の合計バイト数です。 `__LOCAL_SIZE` は、直接のオペランドとしてのみ使用できます。式では使用できません。 このシンボルの値は、変更することも再定義することもできません。 次に例を示します。

```
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov        eax, [ebp - __LOCAL_SIZE]   ;Error
```

次の例では、カスタムのプロローグとエピローグシーケンスを含む生の関数の例では、プロローグシーケンスでシンボルを使用してい `__LOCAL_SIZE` ます。

```cpp
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

[生の関数呼び出し](../cpp/naked-function-calls.md)
