---
title: COlePropertiesDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
ms.openlocfilehash: 37197ee20b31564c589099b10e0f8d3f0d1f7e86
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263872"
---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog クラス

Windows に共通の [OLE プロジェクト プロパティ] ダイアログ ボックスをカプセル化します。

## <a name="syntax"></a>構文

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|`COlePropertiesDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COlePropertiesDialog::DoModal](#domodal)|ダイアログ ボックスを表示しを選択できます。|
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|ドキュメント項目の表示スケールが変更されたときに、フレームワークによって呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COlePropertiesDialog::m_gp](#m_gp)|[全般] ページを初期化するために使用する構造体、`COlePropertiesDialog`オブジェクト。|
|[COlePropertiesDialog::m_lp](#m_lp)|「リンク」ページを初期化するために使用する構造体、`COlePropertiesDialog`オブジェクト。|
|[COlePropertiesDialog::m_op](#m_op)|初期化するために使用する構造体、`COlePropertiesDialog`オブジェクト。|
|[COlePropertiesDialog::m_psh](#m_psh)|追加のカスタム プロパティ ページを追加するために使用する構造体。|
|[COlePropertiesDialog::m_vp](#m_vp)|[表示] ページをカスタマイズするために使用する構造体、`COlePropertiesDialog`オブジェクト。|

## <a name="remarks"></a>Remarks

共通の OLE オブジェクトのプロパティ ダイアログ ボックスでは、表示し、Windows の標準に準拠した形式での OLE ドキュメント項目のプロパティを変更する簡単な方法を提供します。 これらのプロパティには、情報、ドキュメントの項目 (項目がリンクされている) 場合に、項目のリンクをアイコンとイメージのスケーリング、および情報を表示するためのオプションで表されるファイルが、他のユーザーの間で含まれます。

使用する、`COlePropertiesDialog`オブジェクトは、まずを使用してオブジェクトを作成、`COlePropertiesDialog`コンス トラクター。 ダイアログ ボックスが構築された後、`DoModal`メンバー関数 ダイアログ ボックスが表示され、ユーザーが項目のプロパティを変更できるようにします。 `DoModal` ユーザーが [ok] (IDOK) またはキャンセル (IDCANCEL) ボタンを選択したかどうかを返します。 だけでなく、[ok] と [キャンセル] ボタン、[適用] ボタンがあります。 ユーザーは、適用を選択するドキュメント アイテムのプロパティに加えられた変更は、項目に適用されると、そのイメージが自動的に更新しますが、アクティブのままです。

[M_psh](#m_psh)データ メンバーがへのポインター、`PROPSHEETHEADER`構造体、およびほとんどの場合に明示的にアクセスする必要はありません。 既定の [全般]、ビュー、およびリンクのページを超える追加のプロパティ ページを作成する必要がある場合は例外です。 この場合、変更することができます、`m_psh`データ メンバーを呼び出す前に、カスタム ページを含める、`DoModal`メンバー関数。

OLE ダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

##  <a name="colepropertiesdialog"></a>  COlePropertiesDialog::COlePropertiesDialog

`COlePropertiesDialog` オブジェクトを作成します。

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
アクセスされるプロパティを持つドキュメント項目へのポインター。

*nScaleMin*<br/>
ドキュメント項目のイメージの倍率を最小値。

*nScaleMax*<br/>
ドキュメント項目のイメージの倍率の最大値。

*pParentWnd*<br/>
ダイアログ ボックスの親または所有者へのポインター。

### <a name="remarks"></a>Remarks

共通の OLE オブジェクトのプロパティ ダイアログのクラスを派生`COlePropertiesDialog`ドキュメント項目のスケーリングを実装するためにします。 このクラスのインスタンスによって実装されるすべてのダイアログ ボックスでは、ドキュメントの項目のスケーリングはサポートされません。

既定では、共通の OLE オブジェクトのプロパティ ダイアログ ボックスでは、次の 3 つの既定のページがあります。

- 全般

   このページには、選択されているドキュメント項目によって表されるファイルのシステム情報が含まれています。 このページで、ユーザーは、別の型を選択した項目を変換できます。

- 表示

   このページには、アイテムを表示する、アイコンの変更、およびイメージのスケーリングを変更するためのオプションが含まれています。

- Link

   このページには、リンク アイテムの場所を変更して、リンクされた項目を更新するためのオプションが含まれています。 このページで、ユーザーが選択された項目のリンクを中断できます。

既定で提供されるもの以外のページを追加するには、変更、 [m_psh](#m_psh)メンバー変数のコンス トラクターを終了する前に、 `COlePropertiesDialog`-クラスを派生します。 これは、高度な実装、`COlePropertiesDialog`コンス トラクター。

##  <a name="domodal"></a>  COlePropertiesDialog::DoModal

Windows コモン OLE オブジェクトのプロパティ ダイアログ ボックスを表示し、ユーザーが閲覧またはドキュメント アイテムのさまざまなプロパティを変更できるようにするには、このメンバー関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

IDOK や IDCANCEL 成功した場合それ以外の場合 0 を返します。 IDOK や IDCANCEL は、ユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。

IDCANCEL が返された場合、Windows を呼び出すことができます[情報を得る](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror)エラーが発生したかどうかを判断する関数。

##  <a name="m_gp"></a>  COlePropertiesDialog::m_gp

型の構造体[OLEUIGNRLPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuignrlpropsa)OLE オブジェクトのプロパティ ダイアログ ボックスの [全般] ページを初期化するために使用される、します。

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>Remarks

このページは、埋め込みのサイズと種類を表示し、[変換] ダイアログ ボックスへのアクセスを許可します。 このページには、オブジェクトがリンク、リンク先も表示されます。

詳細については、`OLEUIGNRLPROPS`構造体を Windows SDK を参照してください。

##  <a name="m_lp"></a>  COlePropertiesDialog::m_lp

型の構造体[OLEUILINKPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa)OLE オブジェクトのプロパティ ダイアログ ボックスの [リンク] ページを初期化するために使用される、します。

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>Remarks

このページは、リンク アイテムの場所を表示し、更新、またはアイテムへのリンクを解除できます。

詳細については、`OLEUILINKPROPS`構造体を Windows SDK を参照してください。

##  <a name="m_op"></a>  COlePropertiesDialog::m_op

型の構造体[OLEUIOBJECTPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiobjectpropsa)、共通の OLE オブジェクトのプロパティ ダイアログ ボックスを初期化するために使用します。

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>Remarks

この構造体には、[全般]、リンク、およびビュー ページを初期化するために使用されるメンバーが含まれています。

詳細についてを参照してください、OLEUIOBJECTPROPS と[OLEUILINKPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuilinkpropsa) Windows SDK 内の構造体。

##  <a name="m_psh"></a>  COlePropertiesDialog::m_psh

型の構造体[PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2)メンバーを持つダイアログ オブジェクトの特性を格納します。

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>Remarks

構築した後、`COlePropertiesDialog`オブジェクトを使用する`m_psh`を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、`DoModal`メンバー関数。

変更する場合、`m_psh`データ メンバーを直接、既定の動作をオーバーライドします。

詳細については、`PROPSHEETHEADER`構造体を Windows SDK を参照してください。

##  <a name="m_vp"></a>  COlePropertiesDialog::m_vp

型の構造体[OLEUIVIEWPROPS](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiviewpropsa)OLE オブジェクトのプロパティ ダイアログ ボックスの [表示] ページを初期化するために使用される、します。

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>Remarks

このページは、「コンテンツ」と、オブジェクトの「アイコン化」ビューを切り替えると、コンテナー内でスケールを変更できます。 アイコンの変更 ダイアログ ボックスへのユーザー アクセスは、オブジェクトがアイコンとして表示されているときにこともできます。

詳細については、`OLEUIVIEWPROPS`構造体を Windows SDK を参照してください。

##  <a name="onapplyscale"></a>  COlePropertiesDialog::OnApplyScale

スケールの値が変更され、ok または 適用が選択されたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
アクセスされるプロパティを持つドキュメント項目へのポインター。

*nCurrentScale*<br/>
ダイアログのスケールの数値を設定します。

*bRelativeToOrig*<br/>
ドキュメント項目の元のサイズにスケーリングを適用するかどうかを示します。

### <a name="return-value"></a>戻り値

0 以外の値を処理します。それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

既定の実装では、何も行われません。 スケーリングの制御を有効にするには、この関数をオーバーライドする必要があります。

> [!NOTE]
>  共通の OLE オブジェクトのプロパティ ダイアログ ボックスが表示される前にフレームワークのこの関数の場合は NULL を*pItem* - 1 を*nCurrentScale*します。 これは、拡大縮小のコントロールを有効にするかどうかを判断します。

## <a name="see-also"></a>関連項目

[MFC サンプル円](../../visual-cpp-samples.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[CPropertyPage クラス](../../mfc/reference/cpropertypage-class.md)
