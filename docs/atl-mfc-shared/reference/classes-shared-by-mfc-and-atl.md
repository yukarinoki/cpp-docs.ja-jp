---
title: MFC と ATL で共有クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 566164f40f8795c8402b04c9c25e13dda036961d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765438"
---
# <a name="classes-shared-by-mfc-and-atl"></a>MFC と ATL で共有クラス

次の表に、MFC と ATL で共有されるクラス

|クラス|説明|ヘッダー ファイル|
|-----------|-----------------|-----------------|
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|ファイルに関連付けられている日付と時刻の値を管理するためのメソッドを提供します。|atltime.h|
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|相対日付と時刻の値がファイルへの関連付けを管理するためのメソッドを提供します。|atltime.h|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|固定文字バッファーを使用して、文字列オブジェクトを表します。|cstringt.h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|読み込み、JPEG、GIF、BMP、およびポータブル ネットワーク グラフィックス (PNG) 形式で画像を保存する機能など、ビットマップの拡張サポートを提供します。|atlimage.h|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|OLE オートメーションで使用される日付データ型をカプセル化します。|atlcomtime.h|
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|時間間隔の相対的な時間を表します。|atlcomtime.h|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Windows のようなクラス[ポイント](../../mfc/reference/point-structure1.md)も操作するメンバー関数を含む構造`CPoint`と`POINT`構造体。|atltypes.h|
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Windows のようなクラス[RECT](../../mfc/reference/rect-structure1.md)も操作するメンバー関数を含む構造`CRect`オブジェクトと Windows`RECT`構造体。|atltypes.h|
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|表す、`CSimpleStringT`オブジェクト。|atlsimpstr.h|
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Windows のサイズの構造体は、相対座標や位置を実装するようなクラスです。|atltypes.h|
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|リソースの自動クリーンアップは、`GetBuffer`と`ReleaseBuffer`、既存の呼び出す`CStringT`オブジェクト。|atlsimpstr.h|
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|文字列オブジェクトのデータを表します。|atlsimpstr.h|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|表す、`CStringT`オブジェクト。|cstringt.h (MFC 依存) atlstr.h (MFC 依存)|
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|絶対時刻と日付を表します。|atltime.h|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|時間間隔の秒数として内部的に格納されている、時間。|atltime.h|
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|インターフェイスを表す、`CStringT`メモリ マネージャー。|atlsimpstr.h|

## <a name="see-also"></a>関連項目

[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)

