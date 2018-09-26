---
title: 内部リンケージ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09b5a02b7892bff0233e37bbd63020a4d2904ec3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094209"
---
# <a name="internal-linkage"></a>内部リンケージ

オブジェクトまたは関数のファイル スコープ ID の宣言に *storage-class-specifier* **static** が含まれている場合、ID には内部リンケージがあります。 それ以外の場合、識別子は外部リンケージを持ちます。 非終端要素の *storage-class-specifier* の詳細については、「[ストレージ クラス](../c-language/c-storage-classes.md)」をご覧ください。

1 つの翻訳単位内では、内部リンケージを持つ識別子の各インスタンスは、同じ識別子または関数を表します。 内部リンク ID は 1 つの翻訳単位において一意です。

## <a name="see-also"></a>参照

[extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)