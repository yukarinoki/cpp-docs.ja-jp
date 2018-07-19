---
title: 代入 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27e78f7429c4d2a0f83ff7184460eb2ae69df129
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960987"
---
# <a name="assignment"></a>代入
代入演算子 (**=**) は、厳密に言えば、二項演算子。 この宣言は他の二項演算子と同じですが、次の例外があります。  
  
-   非静的メンバー関数である必要があります。 いいえ**演算子 =** 非メンバー関数として宣言することができます。  
  
-   派生クラスにより継承されません。  
  
-   既定の**演算子 =** が存在しない場合、クラス型のためにコンパイラで関数を生成できます。  
  
 次の例では、代入演算子を宣言する方法を示しています。  
  
```cpp 
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 指定された引数が式の右側にあることに注意してください。 演算子は、代入の完了後に左側の値を返す代入演算子の動作を保持するオブジェクトを返します。 これにより、次のようなステートメントを記述できます。  
  
```cpp 
pt1 = pt2 = pt3;  
```  
  
## <a name="see-also"></a>関連項目  
 [演算子のオーバーロード](../cpp/operator-overloading.md)