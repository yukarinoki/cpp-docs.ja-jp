---
title: コンパイラの警告 (レベル 4) C4626
ms.date: 11/04/2016
f1_keywords:
- C4626
helpviewer_keywords:
- C4626
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
ms.openlocfilehash: 665a21d9f0221b2cf3db111142576669a3b5d728
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198265"
---
# <a name="compiler-warning-level-4-c4626"></a>コンパイラの警告 (レベル 4) C4626

'derived class' : 基底クラスの代入演算子がアクセスできないか削除されているため、代入演算子は暗黙的に削除済みとして定義されました

代入演算子は基底クラスで削除されているかアクセスできないため、派生クラスでは生成されません。 この型のオブジェクトを代入しようとすると、コンパイラ エラーが発生します。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4626 を生成し、その修正方法を示しています。

```
// C4626
// compile with: /W4
#pragma warning(default : 4626)
class B
{
// public:
   B& operator = (const B&)
   {
      return *this;
   }
};

class D : public B
{

}; // C4626 - to fix, make B's copy constructor public

int main()
{
   D m;
   D n;
   // m = n;   // this line will cause an error
}
```
