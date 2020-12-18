---
description: '詳細情報: 内部リンケージ'
title: 内部リンケージ
ms.date: 11/04/2016
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
ms.openlocfilehash: a22de598f119ec303cb7ea78255c2537c6ed306e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181866"
---
# <a name="internal-linkage"></a>内部リンケージ

オブジェクトまたは関数のファイル スコープ識別子の宣言に *storage-class-specifier* **`static`** が含まれている場合、その識別子には内部リンケージがあります。 それ以外の場合、識別子は外部リンケージを持ちます。 非終端要素の *storage-class-specifier* の詳細については、「[ストレージ クラス](../c-language/c-storage-classes.md)」をご覧ください。

1 つの翻訳単位内では、内部リンケージを持つ識別子の各インスタンスは、同じ識別子または関数を表します。 内部リンク ID は 1 つの翻訳単位において一意です。

## <a name="see-also"></a>関連項目

[extern を使用したリンケージの指定](../cpp/extern-cpp.md)
