---
title: コンパイラ エラー C3888 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c11c897f35a6c395c4bc6ee6a64be51fa810911b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3888"></a>コンパイラ エラー C3888
'name': このリテラル データ メンバーと関連付けられた const 式は C++/CLI でサポートされていません  
  
 *literal* キーワードを使用して宣言された [name](../../windows/literal-cpp-component-extensions.md) データ メンバーが、コンパイラがサポートしていない値で初期化されています。 コンパイラは、定数の整数型、列挙型、または文字列型のみをサポートしています。 **C3888** エラーの考えられる原因は、データ メンバーがバイト配列で初期化されていることです。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  宣言されたリテラル データ メンバーがサポートされている型であることを確認します。  
  
## <a name="see-also"></a>関連項目  
 [name](../../windows/literal-cpp-component-extensions.md)