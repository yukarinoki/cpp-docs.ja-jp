---
description: '詳細情報: 単純データ型クラス'
title: 単純データ型クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
ms.openlocfilehash: 4ce6e799cc30dddde18a50802e01c872c54d1d3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216965"
---
# <a name="simple-data-type-classes"></a>単純データ型クラス

次のクラスは、描画座標、文字列、および時刻と日付の情報をカプセル化して、C++ 構文を使いやすくします。 これらのオブジェクトは、クラスライブラリの Windows クラスのメンバー関数のパラメーターとして広く使用されています。 `CPoint`、 `CSize` 、およびは、 `CRect` Windows SDK それぞれ **POINT**、 **SIZE**、および **RECT** 構造体に対応しているため、これらの c 言語構造体を使用できる場所であればどこでも、これらの C++ クラスのオブジェクトを使用できます。 クラスは、メンバー関数を介して便利なインターフェイスを提供します。 `CStringT` 非常に柔軟な動的文字列を提供します。 `CTime`、 `COleDateTime` 、 `CTimeSpan` 、およびは、 `COleTimeSpan` 時刻と日付の値を表します。 これらのクラスの詳細については、「 [日付と時刻](../atl-mfc-shared/date-and-time.md)」を参照してください。

"" で始まるクラス `COle` は、OLE によって提供されるデータ型のカプセル化です。 これらのデータ型は、他の OLE 機能が使用されているかどうかに関係なく、Windows プログラムで使用できます。

[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)<br/>
文字列を保持します。

[CTime](../atl-mfc-shared/reference/ctime-class.md)<br/>
絶対時刻と日付の値を保持します。

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE オートメーション型の **日付** のラッパー。 日付と時刻の値を表します。

[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
相対時刻と日付の値を保持します。

[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
2つの値の差など、相対 `COleDateTime` 値を保持し `COleDateTime` ます。

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
座標 (x, y) ペアを保持します。

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
距離、相対位置、またはペアの値を保持します。

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
四角形の領域の座標を保持します。

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Windows イメージリストの機能を提供します。 イメージリストは、リストコントロールおよびツリーコントロールで使用されます。 また、同じサイズのビットマップのセットを格納してアーカイブするために使用することもできます。

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
OLE オートメーション型 **バリアント** のラッパー。 **バリアント型** のデータは、さまざまな形式で格納できます。

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
OLE オートメーション型 **CURRENCY** のラッパー (固定小数点演算型)。小数点の前に15桁、の後に4桁の数値が含まれます。

> [!NOTE]
> `CRect`、 `CSize` 、および `CPoint` は、ATL または MFC アプリケーションで使用できます。 さらに、に `CStringT` は MFC に依存しないようなクラスが用意されて `CString` います。 共有ユーティリティクラスの詳細については、「 [共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)
