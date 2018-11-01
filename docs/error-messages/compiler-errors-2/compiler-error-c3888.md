---
title: コンパイラ エラー C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 067412e59041cb98b68cb373c4671c243ab8a0ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479067"
---
# <a name="compiler-error-c3888"></a>コンパイラ エラー C3888

'name': このリテラル データ メンバーと関連付けられた const 式は C++/CLI でサポートされていません

*literal* キーワードを使用して宣言された [name](../../windows/literal-cpp-component-extensions.md) データ メンバーが、コンパイラがサポートしていない値で初期化されています。 コンパイラは、定数の整数型、列挙型、または文字列型のみをサポートしています。 **C3888** エラーの考えられる原因は、データ メンバーがバイト配列で初期化されていることです。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 宣言されたリテラル データ メンバーがサポートされている型であることを確認します。

## <a name="see-also"></a>関連項目

[name](../../windows/literal-cpp-component-extensions.md)