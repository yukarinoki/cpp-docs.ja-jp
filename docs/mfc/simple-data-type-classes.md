---
title: 単純なデータ型クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54d7f200ee35489f37256023d28bdd3260bf48ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382477"
---
# <a name="simple-data-type-classes"></a>単純データ型クラス
描画の座標、文字列、および時間に、次のクラスがカプセル化し、C++ 構文の日付について、便利な許可を使用します。 これらのオブジェクトは、クラス ライブラリの Windows クラスのメンバー関数をパラメーターとして広く使用されます。 `CPoint`、 `CSize`、および`CRect`に対応している、**ポイント**、**サイズ**、および`RECT`構造体をそれぞれ、Windows sdk には、これらのオブジェクトを使用できますC++ クラスのこれらの C 言語構造体を使用する場合。 クラスは、そのメンバー関数を使用して便利インターフェイスを提供します。 `CStringT` 非常に柔軟な動的文字の文字列を提供します。 `CTime`、 `COleDateTime`、 `CTimeSpan`、および**COleTimeSpan**日付と時刻の値を表します。 これらのクラスの詳細については、記事を参照してください。[日付と時刻](../atl-mfc-shared/date-and-time.md)です。  
  
 クラスで始まる"**コール**"が OLE により提供されるデータ型をカプセル化します。 これらのデータ型は、その他の OLE の機能を使用するかどうかに関係なく、Windows のプログラムで使用できます。  
  
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)  
 文字の文字列を保持します。  
  
 [CTime](../atl-mfc-shared/reference/ctime-class.md)  
 絶対日付と時刻の値を保持します。  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 OLE オートメーション型用のラッパー**日付**です。 日付と時刻の値を表します。  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 相対日付と時刻の値を保持します。  
  
 [メンバー](../atl-mfc-shared/reference/coledatetimespan-class.md)  
 相対を保持`COleDateTime`値、2 つの違いなど`COleDateTime`値。  
  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 ペアは座標 (x, y) を保持します。  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 距離、相対位置、または値のペアを保持します。  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 四角形領域の座標が保持されます。  
  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Windows イメージ リストの機能を提供します。 イメージ リストは、ツリー コントロールとリスト コントロールで使用されます。 格納し、同じサイズのビットマップのセットをアーカイブも使用できます。  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 OLE オートメーション型用のラッパー**バリアント**です。 内のデータ**バリアント**s は、さまざま形式で格納できます。  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 OLE オートメーション型用のラッパー**通貨**、固定小数点の数値型で 15 桁小数点の前に、と後に 4 桁の数字を使用します。  
  
> [!NOTE]
>  `CRect`、 `CSize`、および`CPoint`ATL または MFC のいずれかのアプリケーションでは使用できます。 さらに、`CStringT`提供、MFC に依存しない`CString`-クラスと同様にします。 共有ユーティリティ クラスの詳細については、次を参照してください。[共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

