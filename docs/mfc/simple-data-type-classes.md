---
title: 単純データ型クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
ms.openlocfilehash: d4038334e35b734370a437d35519498b96c00770
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365396"
---
# <a name="simple-data-type-classes"></a>単純データ型クラス

次のクラスは、描画座標、文字列、および時刻と日付の情報をカプセル化し、C++ 構文を使いやすくします。 これらのオブジェクトは、クラス ライブラリの Windows クラスのメンバー関数のパラメーターとして広く使用されています。 、`CPoint``CSize`および`CRect`は、Windows SDK では、それぞれ**POINT** **、SIZE、****および RECT**構造体に対応しているため、これらの C 言語構造を使用できる場所であれば、これらの C++ クラスのオブジェクトを使用できます。 これらのクラスは、メンバー関数を通じて便利なインターフェイスを提供します。 `CStringT`非常に柔軟な動的な文字列を提供します。 `CTime`、、、`COleDateTime``CTimeSpan`および`COleTimeSpan`時刻と日付の値を表します。 これらのクラスの詳細については、「[日付と時刻](../atl-mfc-shared/date-and-time.md)」を参照してください。

" で`COle`始まるクラスは、OLE によって提供されるデータ型のカプセル化です。 これらのデータ型は、他の OLE 機能が使用されているかどうかに関係なく、Windows プログラムで使用できます。

[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)<br/>
文字列を保持します。

[Ctime](../atl-mfc-shared/reference/ctime-class.md)<br/>
絶対時刻と日付の値を保持します。

[Coledatetime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE オートメーションの**ラッパーは**DATE 型です。 日付と時刻の値を表します。

[タイムスパン](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
相対時刻と日付の値を保持します。

[を切り取る](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
2`COleDateTime`つの`COleDateTime`値の差などの相対値を保持します。

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
座標(x,y)のペアを保持します。

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
距離、相対位置、またはペアの値を保持します。

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
矩形領域の座標を保持します。

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Windows イメージ リストの機能を提供します。 イメージ リストは、リスト コントロールおよびツリー コントロールで使用されます。 また、同じサイズのビットマップのセットを格納およびアーカイブするためにも使用できます。

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
OLE オートメーション型**VARIANT**のラッパー 。 **バリアント型**のデータは、さまざまな形式で格納できます。

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
OLE オートメーション型**CURRENCY**のラッパーは、小数点より前に 15 桁、その後 4 桁の固定小数点演算型です。

> [!NOTE]
> `CRect`、、ATL`CSize``CPoint`または MFC アプリケーションで使用できます。 また、MFC`CStringT`に依存しない`CString`-like クラスも提供します。 共有ユーティリティ クラスの詳細については、「[共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)
