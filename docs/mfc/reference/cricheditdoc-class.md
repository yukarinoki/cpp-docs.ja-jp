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
ms.openlocfilehash: 587cf65543e24e586fb8b2336481d6e841473134
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368259"
---
# <a name="cricheditdoc-class"></a>CRichEditDoc クラス

[では](../../mfc/reference/cricheditview-class.md)、MFC のドキュメント[CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)ビュー アーキテクチャのコンテキスト内でリッチ エディット コントロールの機能を提供します。

## <a name="syntax"></a>構文

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の項目を作成します。](#createclientitem)|ドキュメントのクリーンアップを実行するために呼び出されます。|
|[クリッチエディットドク::ゲットストリームフォーマット](#getstreamformat)|ストリームの入力と出力に書式情報を含めるかどうかを示します。|
|[クリッチエディットドック::ゲットビュー](#getview)|関連付けされた[CRichEditView](../../mfc/reference/cricheditview-class.md)オブジェクトを取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[クリッチエディットドック::m_bRTF](#m_brtf)|ストリーム I/O に書式設定を含めるかどうかを示します。|

## <a name="remarks"></a>解説

"リッチ エディット コントロール" とは、ユーザーがテキストを入力および編集できるウィンドウです。 テキストには、文字および段落の書式を割り当てることができ、埋め込み OLE オブジェクトを含めることができます。 リッチ エディット コントロールは、テキストを書式設定するためのプログラミング インターフェイスを提供します。 ただし、アプリケーションは、ユーザーが書式設定操作を使用できるようにするために必要なユーザー インターフェイス コンポーネントを実装する必要があります。

`CRichEditView`は、テキストのテキストと書式設定の特性を維持します。 `CRichEditDoc`は、ビュー内にあるクライアントアイテムのリストを保持します。 `CRichEditCntrItem`は、OLE クライアントアイテムへのコンテナ側アクセスを提供します。

この Windows コモン コントロール (および[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)と関連クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

MFC アプリケーションでリッチ エディット ドキュメントを使用する例については[、WORDPAD](../../overview/visual-cpp-samples.md)サンプル アプリケーションを参照してください。

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

## <a name="cricheditdoccreateclientitem"></a><a name="createclientitem"></a>次の項目を作成します。

`CRichEditCntrItem`オブジェクトを作成し、このドキュメントに追加します。

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>パラメーター

*プレオ*<br/>
OLE アイテムを記述する[REOBJECT](/windows/win32/api/richole/ns-richole-reobject)構造体へのポインター。 この`CRichEditCntrItem`OLE アイテムを中心に新しいオブジェクトが作成されます。 *preo*が NULL の場合、新しいクライアント項目は空です。

### <a name="return-value"></a>戻り値

このドキュメントに追加された新しい[CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

この関数は、OLE 初期化を実行しません。

詳細については、Windows SDK の[REOBJECT](/windows/win32/api/richole/ns-richole-reobject)構造体を参照してください。

## <a name="cricheditdocgetstreamformat"></a><a name="getstreamformat"></a>クリッチエディットドク::ゲットストリームフォーマット

リッチ エディットの内容をストリーミングするためのテキスト形式を決定します。

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>戻り値

次のいずれかのフラグ。

- SF_TEXTリッチ エディット コントロールが書式設定情報を保持しないことを示します。

- SF_RTF リッチ エディット コントロールが書式情報を保持することを示します。

### <a name="remarks"></a>解説

戻り値は[、m_bRTF](#m_brtf)データ メンバーに基づいています。 この関数は、true`m_bRTF`の場合SF_RTF返します。それ以外の場合は、SF_TEXT。

## <a name="cricheditdocgetview"></a><a name="getview"></a>クリッチエディットドック::ゲットビュー

この`CRichEditDoc`オブジェクトに関連付けられている[CRichEditView](../../mfc/reference/cricheditview-class.md)オブジェクトにアクセスします。

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>戻り値

ドキュメントに`CRichEditView`関連付けられているオブジェクトへのポインター。

### <a name="remarks"></a>解説

テキストと書式設定の情報は、オブジェクト内`CRichEditView`に含まれます。 オブジェクト`CRichEditDoc`は、シリアル化用の OLE アイテムを保持します。 1 つにつき`CRichEditView``CRichEditDoc`1 つだけの必要があります。

## <a name="cricheditdocm_brtf"></a><a name="m_brtf"></a>クリッチエディットドック::m_bRTF

TRUE の場合は、[段落](../../mfc/reference/cricheditctrl-class.md#streamin)[と文字](../../mfc/reference/cricheditctrl-class.md#streamout)書式の特性を格納する必要があることを示します。

```
BOOL m_bRTF;
```

## <a name="see-also"></a>関連項目

[MFC サンプル ワードパッド](../../overview/visual-cpp-samples.md)<br/>
[COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスを表示します。](../../mfc/reference/cricheditview-class.md)<br/>
[CRichEditCntrItem クラス](../../mfc/reference/cricheditcntritem-class.md)<br/>
[COleDocument クラス](../../mfc/reference/coledocument-class.md)<br/>
[クラス](../../mfc/reference/cricheditctrl-class.md)
