---
title: アーカイブを通じた CObject の格納と読み込み
ms.date: 11/04/2016
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: 368421a86d6ff6fc70455edd0ea9a32e05645007
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446366"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>アーカイブを通じた CObject の格納と読み込み

アーカイブを介して `CObject`s を格納して読み込むには、追加の考慮事項が必要です。 場合によっては、オブジェクトの `Serialize` 関数を呼び出す必要があります。この場合、`CArchive` オブジェクトは、\<の **<>>** または **`CArchive`** 演算子を使用するのではなく、`Serialize` 呼び出しのパラメーターです。 覚えておくべき重要な事実は、`CArchive` **>>** 演算子は、以前に保存したアーカイブによってファイルに書き込まれた `CRuntimeClass` 情報に基づいて、メモリ内に `CObject` を構築することです。

したがって、`CArchive` **<\<** および **>>** 演算子を使用するかどうかは、`Serialize`の呼び出しとは異なり、以前に格納されていた `CRuntimeClass` 情報に基づいてオブジェクトを動的に再構築するために、読み込みアーカイブ*が必要*かどうかによって異なります。 `Serialize` 関数は、次の場合に使用します。

- オブジェクトを逆シリアル化するときに、オブジェクトの正確なクラスが事前にわかっていることを確認します。

- オブジェクトを逆シリアル化するときに、既にメモリが割り当てられています。

> [!CAUTION]
>  `Serialize` 関数を使用してオブジェクトを読み込む場合は、`Serialize` 関数を使用してオブジェクトを格納する必要もあります。 `CArchive` **<<** 演算子を使用して格納せずに `Serialize` 関数を使用して読み込むか、または `Serialize` 関数を使用して格納してから、`CArchive >>` 演算子を使用して読み込みます。

次に例を示します。

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

要約すると、シリアル化可能なクラスが埋め込み `CObject` をメンバーとして定義する場合は、そのオブジェクトに対して `CArchive` **<\<** および **>>** を使用し*ない*でください。ただし、代わりに `Serialize` 関数を呼び出す必要があります。 また、シリアル化可能なクラスで `CObject` (または `CObject`から派生したオブジェクト) へのポインターがメンバーとして定義されていても、その他のオブジェクトが独自のコンストラクターに構築されている場合は、`Serialize`も呼び出す必要があります。

## <a name="see-also"></a>参照

[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
