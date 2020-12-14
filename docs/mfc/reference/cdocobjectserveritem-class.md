---
description: '詳細情報: CDocObjectServerItem クラス'
title: CDocObjectServerItem クラス
ms.date: 03/27/2019
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnDoVerb
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnDoVerb
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
ms.openlocfilehash: a2d0d924433d812ec5f283d67e8313d20203ca3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184921"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem クラス

OLE サーバー動詞を DocObject サーバー用に実装します。

## <a name="syntax"></a>構文

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|`CDocObjectServerItem` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDocObjectServerItem:: GetDocument](#getdocument)|項目を格納しているドキュメントへのポインターを取得します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CDocObjectServerItem::OnDoVerb](#ondoverb)|動詞を実行するために呼び出されます。|
|[CDocObjectServerItem:: OnHide](#onhide)|フレームワークが DocObject 項目を非表示にしようとすると、例外がスローされます。|
|[CDocObjectServerItem:: OnShow](#onshow)|DocObject 項目が埋め込み先としてアクティブになるように、フレームワークによって呼び出されます。 項目が DocObject でない場合、は [COleServerItem:: OnShow](../../mfc/reference/coleserveritem-class.md#onshow)を呼び出します。|

## <a name="remarks"></a>解説

`CDocObjectServerItem` オーバーライド可能なメンバー関数 ( [Onhide](#onhide)、 [OnDoVerb](#ondoverb)、 [onhide](#onshow)) を定義します。

を使用するには `CDocObjectServerItem` 、派生クラスの [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) オーバーライドによって新しいオブジェクトが返されることを確認し `COleServerDoc` `CDocObjectServerItem` ます。 項目の機能を変更する必要がある場合は、独自の派生クラスの新しいインスタンスを作成でき `CDocObjectServerItem` ます。

DocObjects の詳細については、 *MFC リファレンス* の [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) and [COleCmdUI](../../mfc/reference/colecmdui-class.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>要件

**ヘッダー:** afxdocob

## <a name="cdocobjectserveritemcdocobjectserveritem"></a><a name="cdocobjectserveritem"></a> CDocObjectServerItem::CDocObjectServerItem

`CDocObjectServerItem` オブジェクトを構築します。

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>パラメーター

*pServerDoc*<br/>
新しい DocObject item を格納するドキュメントへのポインター。

*bAutoDelete*<br/>
オブジェクトへのリンクが解放されたときにオブジェクトを削除できるかどうかを示します。 `CDocObjectServerItem`オブジェクトがドキュメントのデータの重要な部分である場合は、引数を FALSE に設定します。 オブジェクトが、フレームワークによって削除できるドキュメントのデータ内の範囲を識別するために使用される二次的な構造体である場合は、TRUE に設定します。

## <a name="cdocobjectserveritemgetdocument"></a><a name="getdocument"></a> CDocObjectServerItem:: GetDocument

項目を格納しているドキュメントへのポインターを取得します。

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>戻り値

項目を格納しているドキュメントへのポインター。項目がドキュメントの一部でない場合は NULL。

### <a name="remarks"></a>解説

これにより、 [CDocObjectServerItem](#cdocobjectserveritem) コンストラクターに引数として渡されたサーバードキュメントにアクセスできるようになります。

## <a name="cdocobjectserveritemondoverb"></a><a name="ondoverb"></a> CDocObjectServerItem::OnDoVerb

指定された動詞を実行するためにフレームワークによって呼び出されます。

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>パラメーター

*iVerb*<br/>
実行する動詞を指定します。 使用可能な値については、Windows SDK の「 [IOleObject::D oVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) 」を参照してください。

### <a name="remarks"></a>解説

項目が DocObject で、OLEIVERB_INPLACEACTIVATE または OLEIVERB_SHOW が指定されている場合、既定の実装は [Onshow](#onshow) メンバー関数を呼び出します。 項目が DocObject でない場合、または別の動詞が指定されている場合、既定の実装は、 [COleServerItem:: OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb)を呼び出します。

## <a name="cdocobjectserveritemonhide"></a><a name="onhide"></a> CDocObjectServerItem:: OnHide

項目を非表示にするためにフレームワークによって呼び出されます。

```
virtual void OnHide();
```

### <a name="remarks"></a>解説

項目が DocObject の場合、既定の実装は例外をスローします。 アクティブな DocObject 項目はビュー全体を使用するため、非表示にすることはできません。 DocObject 項目を非アクティブ化して、非表示にする必要があります。 項目が DocObject でない場合、既定の実装は、 [COleServerItem:: OnHide](../../mfc/reference/coleserveritem-class.md#onhide)を呼び出します。

## <a name="cdocobjectserveritemonshow"></a><a name="onshow"></a> CDocObjectServerItem:: OnShow

DocObject 項目をアクティブにするようにサーバーアプリケーションに指示するために、フレームワークによって呼び出されます。

```
virtual void OnShow();
```

### <a name="remarks"></a>解説

項目が DocObject でない場合、既定の実装は、 [COleServerItem:: OnShow](../../mfc/reference/coleserveritem-class.md#onopen)を呼び出します。 DocObject 項目を開くときに特別な処理を実行する場合は、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServer クラス](../../mfc/reference/cdocobjectserver-class.md)<br/>
[COleDocObjectItem クラス](../../mfc/reference/coledocobjectitem-class.md)
