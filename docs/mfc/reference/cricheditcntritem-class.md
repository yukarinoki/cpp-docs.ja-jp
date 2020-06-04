---
title: CRichEditCntrItem クラス
ms.date: 11/04/2016
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
ms.openlocfilehash: 7b566fe7f1c0667dbcdb4976f79cd2e1597f48f6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752773"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem クラス

[では](../../mfc/reference/cricheditview-class.md)、MFC のドキュメント[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)ビュー アーキテクチャのコンテキスト内でリッチ エディット コントロールの機能を提供します。

## <a name="syntax"></a>構文

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の項目を選択します。](#cricheditcntritem)|`CRichEditCntrItem` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトを編集します。](#synctoricheditobject)|アイテムを別の種類としてアクティブにします。|

## <a name="remarks"></a>解説

"リッチ エディット コントロール" とは、ユーザーがテキストを入力および編集できるウィンドウです。 テキストには、文字および段落の書式を割り当てることができ、埋め込み OLE オブジェクトを含めることができます。 リッチ エディット コントロールは、テキストを書式設定するためのプログラミング インターフェイスを提供します。 ただし、アプリケーションは、ユーザーが書式設定操作を使用できるようにするために必要なユーザー インターフェイス コンポーネントを実装する必要があります。

`CRichEditView`は、テキストのテキストと書式設定の特性を維持します。 `CRichEditDoc`は、ビュー内にある OLE クライアントアイテムのリストを保持します。 `CRichEditCntrItem`は、OLE クライアントアイテムへのコンテナ側アクセスを提供します。

この Windows コモン コントロール (および[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)と関連クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

MFC アプリケーションでリッチ エディット コンテナー項目を使用する例については[、WORDPAD](../../overview/visual-cpp-samples.md)サンプル アプリケーションを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrich.h

## <a name="cricheditcntritemcricheditcntritem"></a><a name="cricheditcntritem"></a>次の項目を選択します。

`CRichEditCntrItem`オブジェクトを作成し、コンテナー ドキュメントに追加します。

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>パラメーター

*プレオ*<br/>
OLE アイテムを記述する[REOBJECT](/windows/win32/api/richole/ns-richole-reobject)構造体へのポインター。 この`CRichEditCntrItem`OLE アイテムを中心に新しいオブジェクトが作成されます。 *preo*が NULL の場合、クライアント項目は空です。

*pContainer*<br/>
この項目を含むコンテナー ドキュメントへのポインター。 *pContainer が*NULL の場合は、明示的に[COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem)を呼び出して、このクライアント項目をドキュメントに追加する必要があります。

### <a name="remarks"></a>解説

この関数は、OLE 初期化を実行しません。

詳細については、Windows SDK の[REOBJECT](/windows/win32/api/richole/ns-richole-reobject)構造体を参照してください。

## <a name="cricheditcntritemsynctoricheditobject"></a><a name="synctoricheditobject"></a>オブジェクトを編集します。

この関数を呼び出して、デバイス`CRichEditCntrltem`の側面である DVASPECT を*reo*で指定されたデバイスのア[スペクト](/windows/win32/api/wtypes/ne-wtypes-dvaspect)と同期させます。

```cpp
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>パラメーター

*Reo*<br/>
OLE アイテムを記述する[REOBJECT](/windows/win32/api/richole/ns-richole-reobject)構造体への参照。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[「DVASPECT」](/windows/win32/api/wtypes/ne-wtypes-dvaspect)を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル ワードパッド](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/coleclientitem-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cricheditview-class.md)
