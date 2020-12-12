---
description: '詳細については、「シリアル化: オブジェクトのシリアル化」を参照してください。'
title: 'シリアル化 : オブジェクトのシリアル化'
ms.date: 11/04/2016
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
ms.openlocfilehash: ec0782f7faa0d6400f40013925f4a53495a76c7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217474"
---
# <a name="serialization-serializing-an-object"></a>シリアル化 : オブジェクトのシリアル化

「 [シリアル化:](../mfc/serialization-making-a-serializable-class.md) シリアル化可能なクラスの作成」では、クラスをシリアル化可能にする方法を示しています。 Serializable クラスを作成すると、そのクラスのオブジェクトを、 [CArchive](../mfc/reference/carchive-class.md) オブジェクトを介して、ファイルとの間でシリアル化できます。 この記事では、以下の内容について説明しています。

- [CArchive オブジェクトとは何ですか](../mfc/what-is-a-carchive-object.md)。

- [2 つの方法で CArchive を作成](../mfc/two-ways-to-create-a-carchive-object.md)できます。

- [CArchive <\< and >> 演算子の使用方法](../mfc/using-the-carchive-output-and-input-operators.md)。

- [アーカイブを使用した通じた cobject の格納と読み込み](../mfc/storing-and-loading-cobjects-via-an-archive.md)。

フレームワークでは、シリアル化可能なドキュメントのアーカイブを作成することも、明示的にオブジェクトを作成することもでき `CArchive` ます。 \< and >またはの <> 演算子を使用する `CArchive` か、場合によっては `Serialize` 派生クラスの関数を呼び出すことによって、ファイルとシリアル化可能なオブジェクトとの間でデータを転送でき `CObject` ます。

## <a name="see-also"></a>関連項目

[シリアル化](../mfc/serialization-in-mfc.md)
