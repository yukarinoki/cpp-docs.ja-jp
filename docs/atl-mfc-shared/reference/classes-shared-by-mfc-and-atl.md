---
description: 詳細については、「MFC と ATL で共有されるクラス」を参照してください。
title: MFC と ATL で共有されるクラス
ms.date: 11/04/2016
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
ms.openlocfilehash: df196f92b7b16742545a7d82320ef4fe8da77fe2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166786"
---
# <a name="classes-shared-by-mfc-and-atl"></a>MFC と ATL で共有されるクラス

次の表は、MFC と ATL の間で共有されるクラスを示しています。

|クラス|説明|ヘッダー ファイル|
|-----------|-----------------|-----------------|
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|ファイルに関連付けられた日付と時刻の値を管理するためのメソッドを提供します。|atltime. h|
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|ファイルに関連付けられている相対的な日付と時刻の値を管理するためのメソッドを提供します。|atltime. h|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|固定文字バッファーを持つ文字列オブジェクトを表します。|cstringt|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|では、JPEG、GIF、BMP、およびポータブルネットワークグラフィックス (PNG) 形式のイメージを読み込んで保存する機能など、ビットマップのサポートが強化されています。|atlimage|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|OLE オートメーションで使用される日付データ型をカプセル化します。|atlcomtime .h|
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|時間間隔の相対時間を表します。|atlcomtime .h|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|構造体を操作するためのメンバー関数も含む、Windows [ポイント](/windows/win32/api/windef/ns-windef-point) 構造体に似たクラス `CPoint` `POINT` 。|atltypes. h|
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|[](/windows/win32/api/windef/ns-windef-rect) `CRect` オブジェクトおよび windows 構造体を操作するためのメンバー関数も含む、Windows の RECT 構造体に似たクラス `RECT` 。|atltypes. h|
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|`CSimpleStringT` オブジェクトを表します。|atl、pstr .h|
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|相対座標または位置を実装する Windows の [サイズ](/windows/win32/api/windef/ns-windef-size) 構造体に似たクラス。|atltypes. h|
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|既存のオブジェクトに対してとを呼び出すための自動リソースクリーンアップを提供 `GetBuffer` し `ReleaseBuffer` `CStringT` ます。|atl、pstr .h|
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|String オブジェクトのデータを表します。|atl、pstr .h|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|`CStringT` オブジェクトを表します。|cstringt (MFC 依存) atlstr .h (MFC 非依存)|
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|絶対時刻と日付を表します。|atltime. h|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|期間内の秒数として内部的に格納される時間。|atltime. h|
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|メモリマネージャーへのインターフェイスを表し `CStringT` ます。|atl、pstr .h|

## <a name="see-also"></a>関連項目

[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
