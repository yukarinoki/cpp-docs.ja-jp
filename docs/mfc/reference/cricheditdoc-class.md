---
title: CRichEditDoc クラス
ms.date: 11/04/2016
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
ms.openlocfilehash: 4cc3af7649d30a153b67cd8269e595c11018833f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372089"
---
# <a name="cricheditdoc-class"></a>CRichEditDoc クラス

[CRichEditView](../../mfc/reference/cricheditview-class.md)と[CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)MFC のドキュメント ビュー アーキテクチャのコンテキストでリッチ エディット コントロールの機能を提供します。

## <a name="syntax"></a>構文

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRichEditDoc::CreateClientItem](#createclientitem)|ドキュメントのクリーンアップを実行すると呼ばれます。|
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|ストリーム入力と出力が書式設定情報を含めるかどうかを示します。|
|[CRichEditDoc::GetView](#getview)|取得、関連付けられている[CRichEditView](../../mfc/reference/cricheditview-class.md)オブジェクト。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CRichEditDoc::m_bRTF](#m_brtf)|ストリーム入出力が書式設定を含めるかどうかを示します。|

## <a name="remarks"></a>Remarks

「リッチ エディット コントロール」をユーザーは入力し、テキストの編集ウィンドウです。 テキストは、文字および段落の書式設定に割り当てることができるし、埋め込み OLE オブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストの書式設定のプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーに使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。

`CRichEditView` テキストとテキストの書式設定特性を保持します。 `CRichEditDoc` ビュー内にあるクライアント アイテムの一覧を保持します。 `CRichEditCntrItem` コンテナー側 OLE クライアントのアイテムへのアクセスを提供します。

この Windows コモン コントロール (つまり、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)および関連クラス) は以降 Windows 95/98 および Windows NT 3.51 の下で実行中のプログラムにのみ使用できます。

リッチ エディット ドキュメントを使用して MFC アプリケーションでの例は、次を参照してください。、[ワードパッド](../../overview/visual-cpp-samples.md)サンプル アプリケーション。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrich.h

##  <a name="createclientitem"></a>  CRichEditDoc::CreateClientItem

作成するには、この関数を呼び出し、`CRichEditCntrItem`オブジェクトし、このドキュメントに追加します。

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>パラメーター

*preo*<br/>
ポインター、 [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) OLE 項目を記述する構造体。 新しい`CRichEditCntrItem`この OLE アイテム オブジェクトが構築されます。 場合*preo*が null の場合、新しいクライアントの項目が空です。

### <a name="return-value"></a>戻り値

新しいへのポインター [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)オブジェクトがこのドキュメントに追加されました。

### <a name="remarks"></a>Remarks

この関数では、OLE の初期化は実行されません。

詳細については、次を参照してください。、 [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Windows SDK の構造体。

##  <a name="getstreamformat"></a>  CRichEditDoc::GetStreamFormat

リッチ エディットのコンテンツをストリームのテキスト形式を判断するには、この関数を呼び出します。

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>戻り値

次のフラグのいずれか:

- SF_TEXT では、リッチ エディット コントロールであることを示しますが、書式設定情報は保持されません。

- SF_RTF では、リッチ エディット コントロールであることを示します、書式設定情報は保持します。

### <a name="remarks"></a>Remarks

戻り値がに基づいて、 [m_bRTF](#m_brtf)データ メンバー。 場合、この関数は SF_RTF を返します`m_bRTF`TRUE。 それ以外は SF_TEXT します。

##  <a name="getview"></a>  CRichEditDoc::GetView

アクセスするには、この関数を呼び出して、 [CRichEditView](../../mfc/reference/cricheditview-class.md)オブジェクトに関連付けられた`CRichEditDoc`オブジェクト。

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>戻り値

ポインター、`CRichEditView`ドキュメントに関連付けられているオブジェクト。

### <a name="remarks"></a>Remarks

テキストと書式設定情報内に含まれる、`CRichEditView`オブジェクト。 `CRichEditDoc`オブジェクトはシリアル化のために OLE 項目を保持します。 1 つだけあります`CRichEditView`各`CRichEditDoc`します。

##  <a name="m_brtf"></a>  CRichEditDoc::m_bRTF

TRUE の場合、ことを示します。 [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin)と[CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout)段落と文字書式の特性を格納する必要があります。

```
BOOL m_bRTF;
```

## <a name="see-also"></a>関連項目

[ワードパッドの MFC サンプル](../../overview/visual-cpp-samples.md)<br/>
[COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRichEditView クラス](../../mfc/reference/cricheditview-class.md)<br/>
[CRichEditCntrItem クラス](../../mfc/reference/cricheditcntritem-class.md)<br/>
[COleDocument クラス](../../mfc/reference/coledocument-class.md)<br/>
[CRichEditCtrl クラス](../../mfc/reference/cricheditctrl-class.md)
