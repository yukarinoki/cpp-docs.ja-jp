---
description: 詳細については、アーカイブを使用した通じた cobject の格納と読み込みに関するページを参照してください。
title: アーカイブを通じた CObject の格納と読み込み
ms.date: 11/04/2016
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: c84c507fc556268eea526c1350211fd4b82f54fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216562"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>アーカイブを通じた CObject の格納と読み込み

アーカイブを使用して s を格納して読み込む `CObject` には、別途考慮が必要です。 場合によっては、オブジェクトの関数を呼び出す必要があります。この場合、 `Serialize` `CArchive` オブジェクトは `Serialize` **<\<** or **>>** 、の演算子を使用するのではなく、呼び出しのパラメーターです `CArchive` 。 注意すべき重要な事実は、 `CArchive` **>>** `CObject` `CRuntimeClass` 格納アーカイブによって以前にファイルに書き込まれた情報に基づいて、演算子によってがメモリに構築されることです。

したがって、演算子を使用するかどうかは、 `CArchive` **<\<** and **>>** `Serialize` 以前に保存された情報に基づいてオブジェクトを動的に再構築するために、読み込みアーカイブ *が必要* かどうかによって異なり `CRuntimeClass` ます。 次の場合は、関数を使用し `Serialize` ます。

- オブジェクトを逆シリアル化するときに、オブジェクトの正確なクラスが事前にわかっていることを確認します。

- オブジェクトを逆シリアル化するときに、既にメモリが割り当てられています。

> [!CAUTION]
> 関数を使用してオブジェクトを読み込む場合は、 `Serialize` 関数を使用してオブジェクトも格納する必要があり `Serialize` ます。 演算子を使用して格納せずに、関数を使用して読み込むか、または関数を使用して格納し、 `CArchive` **<<** `Serialize` `Serialize` 次に演算子を使用して読み込み `CArchive >>` ます。

次に例を示します。

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

要約すると、シリアル化可能なクラスでメンバーとして埋め込まれたが定義されている場合は、 `CObject` そのオブジェクトに対して演算子を使用し *ない* でください `CArchive` **<\<** and **>>** 。ただし、代わりに関数を呼び出す必要があり `Serialize` ます。 また、シリアル化可能なクラスで、 `CObject` メンバーとして (またはから派生したオブジェクト) へのポインターが定義さ `CObject` れていて、その他のオブジェクトが独自のコンストラクターに構築されている場合も、を呼び出す必要があり `Serialize` ます。

## <a name="see-also"></a>関連項目

[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
