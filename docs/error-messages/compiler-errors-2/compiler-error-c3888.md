---
title: コンパイラ エラー C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 20251292ec4635ea855a56890878bc55f567ab62
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777468"
---
# <a name="compiler-error-c3888"></a>コンパイラ エラー C3888

'name': このリテラル データ メンバーと関連付けられた const 式は C++/CLI でサポートされていません

*literal* キーワードを使用して宣言された [name](../../extensions/literal-cpp-component-extensions.md) データ メンバーが、コンパイラがサポートしていない値で初期化されています。 コンパイラは、定数の整数型、列挙型、または文字列型のみをサポートしています。 **C3888** エラーの考えられる原因は、データ メンバーがバイト配列で初期化されていることです。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 宣言されたリテラル データ メンバーがサポートされている型であることを確認します。

## <a name="see-also"></a>関連項目

[name](../../extensions/literal-cpp-component-extensions.md)