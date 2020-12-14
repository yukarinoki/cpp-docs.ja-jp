---
description: 詳細については、「コンパイラエラー C3888」を参照してください。
title: コンパイラ エラー C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 5b47d78d0d6c75f4bdd266f95fff2ce4ab025d4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274321"
---
# <a name="compiler-error-c3888"></a>コンパイラ エラー C3888

'name': このリテラル データ メンバーと関連付けられた const 式は C++/CLI でサポートされていません

*literal* キーワードを使用して宣言された [name](../../extensions/literal-cpp-component-extensions.md) データ メンバーが、コンパイラがサポートしていない値で初期化されています。 コンパイラは、定数の整数型、列挙型、または文字列型のみをサポートしています。 **C3888** エラーの考えられる原因は、データ メンバーがバイト配列で初期化されていることです。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 宣言されたリテラル データ メンバーがサポートされている型であることを確認します。

## <a name="see-also"></a>関連項目

[literal](../../extensions/literal-cpp-component-extensions.md)
