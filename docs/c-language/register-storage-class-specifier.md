---
description: '詳細情報: register ストレージ クラス指定子'
title: register ストレージ クラス指定子
ms.date: 11/04/2016
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
ms.openlocfilehash: a7e062f72191f6ee6d678d18b902ea184d362714
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120758"
---
# <a name="register-storage-class-specifier"></a>register ストレージ クラス指定子

**Microsoft 固有の仕様**

Microsoft C/C++ コンパイラは、レジスタ変数に対するユーザーの要求を考慮しません。 ただし、移植性を考慮して、 **`register`** キーワードに関連付けられた他のセマンティクスは、すべてコンパイラによって実行されます。 たとえば、レジスタ オブジェクトに単項アドレス演算子 ( **&** ) を適用することはできず、配列で **`register`** キーワードを使用することもできません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[内部レベル宣言のストレージ クラス指定子](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
