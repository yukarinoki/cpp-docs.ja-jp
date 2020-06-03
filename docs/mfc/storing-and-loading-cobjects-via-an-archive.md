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
ms.openlocfilehash: f1b59516d5bba13b6f5e006f91d8ebd560543b05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372146"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>アーカイブを通じた CObject の格納と読み込み

アーカイブ経由で`CObject`の s の保存と読み込みには、追加の考慮事項が必要です。 場合によっては、オブジェクトの`Serialize`関数を呼び出す必要があります。 `CArchive` `Serialize` ** < ** **>>** `CArchive` 重要な点は、`CArchive`**>>** 格納アーカイブによってファイル`CObject`に書き込まれた情報に`CRuntimeClass`基づいて、オペレータがインメモリを構築することです。

したがって`CArchive`**<**、 演算子と**>>** 演算子を使用するかどうか、`Serialize`と を呼び出すのとは、 以前に格納された`CRuntimeClass`情報に基づいてオブジェクトを動的に再構築するために、ロード・アーカイブが*必要*かどうかによって異なります。 この関数`Serialize`は、次の場合に使用します。

- オブジェクトを逆シリアル化する場合は、オブジェクトの正確なクラスを事前に把握しておく必要があります。

- オブジェクトを逆シリアル化する場合、メモリが割り当て済みである。

> [!CAUTION]
> 関数を使用してオブジェクトをロード`Serialize`する場合は、 関数を使用してオブジェクト`Serialize`も格納する必要があります。 演算子を使用して格納してから`CArchive`**<<** 関数を`Serialize`使用して読み込んだり、関数を`Serialize`使用して格納してから演算子を`CArchive >>`使用して読み込んだりしないでください。

次の例は、ケースを示しています。

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

つまり、シリアル化可能なクラスで埋め込`CObject`み型のメンバーとして定義されている場合は`CArchive`**<**、**>>** オブジェクトに and 演算子を使用`Serialize`*するのではなく*、代わりに関数を呼び出す必要があります。 また、シリアル化可能なクラスで`CObject`、 または`CObject`から派生した オブジェクトへのポインターをメンバーとして定義し、その他のオブジェクトを独自のコンストラクターに構築する場合は`Serialize`、 も呼び出す必要があります。

## <a name="see-also"></a>関連項目

[シリアル化 : オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
