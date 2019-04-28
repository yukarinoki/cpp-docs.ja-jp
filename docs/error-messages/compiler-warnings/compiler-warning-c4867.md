---
title: コンパイラの警告 C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: 9fa9b382b42a2fb8ba72fd9744c612af5dd598d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311073"
---
# <a name="compiler-warning-c4867"></a>コンパイラの警告 C4867

'function': 関数呼び出しの引数リストがありません。'call' を使用して、メンバーへのポインターを作成するには

メンバー関数へのポインターが正しく初期化されていません。

この警告は、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成できます。 準拠が強化されたメンバーへのポインター。  Visual C 2005 より前にコンパイルされたコードには、今すぐ C4867 が生成されます。

この警告は、常にエラーとして表示されます。 この警告を無効にするには、 [warning](../../preprocessor/warning.md) プラグマを使用します。 C4867 と MFC と ATL の詳細については、次を参照してください。 [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning)します。

## <a name="example"></a>例

次の例では、C4867 が生成されます。

```
// C4867.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b = {f};   // C4867
      B b2 = {&A::f};   // OK
   }
};
```