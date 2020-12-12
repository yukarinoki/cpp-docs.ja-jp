---
description: 詳細については、「コンパイラエラー C2978」を参照してください。
title: コンパイラ エラー C2978
ms.date: 11/04/2016
f1_keywords:
- C2978
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
ms.openlocfilehash: 7f39b6d7b01790bd8865c4e176ff8ed865756edb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281822"
---
# <a name="compiler-error-c2978"></a>コンパイラ エラー C2978

構文エラー: 'keyword1' または 'keyword2' が必要ですが、型 'keyword3' が見つかりました。非型パラメーターはジェネリックではサポートされていません

ジェネリック クラスの宣言が正しくありません。 詳細については、「 [ジェネリック](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C2978 が生成されます。

```cpp
// C2978.cpp
// compile with: /clr /c
generic <ref class T>   // C2978
// try the following line instead
// generic <typename T>   // OK
ref class Utils {
   static void sort(T elems, size_t size);
};

generic <int>
// try the following line instead
// generic <class T>
ref class Utils2 {
   static void sort(T elems, size_t size);
};
```
