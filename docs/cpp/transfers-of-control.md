---
title: 制御の移動
ms.date: 11/04/2016
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
ms.openlocfilehash: c9a46ccb1cf519080c5105855e41ecd3ebc23f77
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188052"
---
# <a name="transfers-of-control"></a>制御の移動

**Switch**ステートメントで**goto**ステートメントまたは**case**ラベルを使用して、初期化子を越えて分岐するプログラムを指定できます。 初期化子を含む宣言がジャンプ ステートメントの発生元のブロックで囲まれたブロックに存在しない限り、このようなコードは無効です。

次の例は、オブジェクト `total`、`ch`、`i` を宣言して初期化するループを示します。 また、初期化子を超えて制御を転送する、間違った**goto**ステートメントもあります。

```cpp
// transfers_of_control.cpp
// compile with: /W1
// Read input until a nonnumeric character is entered.
int main()
{
   char MyArray[5] = {'2','2','a','c'};
   int i = 0;
   while( 1 )
   {
      int total = 0;

      char ch = MyArray[i++];

      if ( ch >= '0' && ch <= '9' )
      {
         goto Label1;

         int i = ch - '0';
      Label1:
         total += i;   // C4700: transfers past initialization of i.
      } // i would be destroyed here if  goto error were not present
   else
      // Break statement transfers control out of loop,
      //  destroying total and ch.
      break;
   }
}
```

前の例では、 **goto**ステートメントは、`i`の初期化を超えて制御を転送しようとします。 ただし、`i` が宣言されていても初期化されていない場合、転送は有効になります。

**While**ステートメントの*ステートメント*として機能するブロックで宣言された `total` および `ch`のオブジェクトは、 **break**ステートメントを使用してブロックが終了したときに破棄されます。
