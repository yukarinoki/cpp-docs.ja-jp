---
title: コンパイラ エラー C2978 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2978
dev_langs:
- C++
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cabf938343b375fdd27647711bb3e5b1d1f16d39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245000"
---
# <a name="compiler-error-c2978"></a>コンパイラ エラー C2978
構文エラー: 'keyword1' または 'keyword2' が必要ですが、型 'keyword3' が見つかりました。非型パラメーターはジェネリックではサポートされていません  
  
 ジェネリック クラスの宣言が正しくありません。 参照してください[ジェネリック](../../windows/generics-cpp-component-extensions.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C2978 が生成されます。  
  
```  
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