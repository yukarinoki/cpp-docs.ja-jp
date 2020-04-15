---
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
ms.openlocfilehash: 1f0f5cf93aab35a17f7174b2beee0d1398564a3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375528"
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
|[オブジェクトサーバーアイテム::CDoc オブジェクトサーバーアイテム](#cdocobjectserveritem)|`CDocObjectServerItem` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトサーバーアイテム::ドキュメントを取得します。](#getdocument)|項目を含むドキュメントへのポインターを取得します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#ondoverb)|動詞を実行するために呼び出されます。|
|[オブジェクトサーバーアイテム::オンハイド](#onhide)|フレームワークが DocObject 項目を非表示にしようとすると、例外をスローします。|
|[サービス提供::オンショー](#onshow)|DocObject 項目を埋め込み先編集中にアクティブにするために、フレームワークによって呼び出されます。 アイテムが DocObject でない場合は[、COle サーバーアイテム::オンショー](../../mfc/reference/coleserveritem-class.md#onshow)を呼び出します。|

## <a name="remarks"></a>解説

`CDocObjectServerItem`オーバーライド可能なメンバー関数を定義します: [OnHide](#onhide)、 [OnDoVerb](#ondoverb)、および[OnShow](#onshow)。

を使用`CDocObjectServerItem`するには、派生クラスの[OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)オーバーライド`COleServerDoc`が新しい`CDocObjectServerItem`オブジェクトを返すことを確認します。 アイテムの機能を変更する必要がある場合は、独自`CDocObjectServerItem`の派生クラスの新しいインスタンスを作成できます。

DocObject の詳細については *、MFC リファレンス*の[「CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)と[COleCmdUI」](../../mfc/reference/colecmdui-class.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdocob.h

## <a name="cdocobjectserveritemcdocobjectserveritem"></a><a name="cdocobjectserveritem"></a>オブジェクトサーバーアイテム::CDoc オブジェクトサーバーアイテム

`CDocObjectServerItem` オブジェクトを構築します。

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
新しい DocObject アイテムを含むドキュメントへのポインター。

*b自動削除*<br/>
オブジェクトへのリンクが解放されたときにオブジェクトを削除できるかどうかを示します。 オブジェクトがドキュメントのデータの`CDocObjectServerItem`不可欠な部分である場合は、引数を FALSE に設定します。 フレームワークによって削除できるドキュメントのデータの範囲を識別するために使用される 2 次構造である場合は、TRUE に設定します。

## <a name="cdocobjectserveritemgetdocument"></a><a name="getdocument"></a>オブジェクトサーバーアイテム::ドキュメントを取得します。

項目を含むドキュメントへのポインターを取得します。

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>戻り値

アイテムを含むドキュメントへのポインター。アイテムがドキュメントの一部でない場合は NULL。

### <a name="remarks"></a>解説

これにより、引数として渡されたサーバー ドキュメントへのアクセスが[許可](#cdocobjectserveritem)されます。

## <a name="cdocobjectserveritemondoverb"></a><a name="ondoverb"></a>をクリックします。

指定された動詞を実行するために、フレームワークによって呼び出されます。

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>パラメーター

*i動詞*<br/>
実行する動詞を指定します。 可能な値については、次[を :D参照してください。](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)

### <a name="remarks"></a>解説

項目が DocObject で、OLEIVERB_INPLACEACTIVATEまたはOLEIVERB_SHOWが指定されている場合、既定の実装は[OnShow](#onshow)メンバー関数を呼び出します。 項目が DocObject でない場合、または別の動詞が指定されている場合、既定の実装は[COleServerItem::OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb)を呼び出します。

## <a name="cdocobjectserveritemonhide"></a><a name="onhide"></a>オブジェクトサーバーアイテム::オンハイド

アイテムを非表示にするために、フレームワークによって呼び出されます。

```
virtual void OnHide();
```

### <a name="remarks"></a>解説

項目が DocObject の場合、既定の実装では例外がスローされます。 アクティブな DocObject アイテムはビュー全体を使用するため、非表示にできません。 DocObject アイテムを非表示にするには、その項目を非アクティブ化する必要があります。 アイテムが DocObject でない場合、既定の実装は[COleServerItem::OnHide を](../../mfc/reference/coleserveritem-class.md#onhide)呼び出します。

## <a name="cdocobjectserveritemonshow"></a><a name="onshow"></a>サービス提供::オンショー

DocObject 項目を埋め込み先編集用にアクティブにするようにサーバー アプリケーションに指示するために、フレームワークによって呼び出されます。

```
virtual void OnShow();
```

### <a name="remarks"></a>解説

アイテムが DocObject でない場合、既定の実装は[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen)を呼び出します。 DocObject アイテムを開くときに特別な処理を実行する場合は、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServer クラス](../../mfc/reference/cdocobjectserver-class.md)<br/>
[クラス](../../mfc/reference/coledocobjectitem-class.md)
