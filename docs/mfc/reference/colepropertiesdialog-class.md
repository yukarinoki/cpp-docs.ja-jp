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
ms.openlocfilehash: f065894ff49af755ab4020f71b0213b19db49054
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374896"
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
|[ダイアログ ボックス::プロパティダイアログ](#colepropertiesdialog)|`COlePropertiesDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::Do モーダル](#domodal)|ダイアログ ボックスを表示し、ユーザーが選択できるようにします。|
|[コントロールプロパティダイアログ::オンApplyスケール](#onapplyscale)|ドキュメント アイテムのスケーリングが変更されたときに、フレームワークによって呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_gp](#m_gp)|オブジェクトの 「一般」ページを初期化するために使用`COlePropertiesDialog`される構造体。|
|[ダイアログ::m_lp](#m_lp)|オブジェクトの "Link" ページを初期化するために使用`COlePropertiesDialog`される構造体。|
|[ダイアログ::m_op](#m_op)|オブジェクトの初期化に使用される`COlePropertiesDialog`構造体。|
|[ダイアログ::m_psh](#m_psh)|カスタム プロパティ ページを追加するために使用する構造体。|
|[プロパティダイアログ::m_vp](#m_vp)|`COlePropertiesDialog`オブジェクトの "表示" ページをカスタマイズするための構造体。|

## <a name="remarks"></a>解説

[OLE オブジェクトのプロパティ] ダイアログ ボックスを使用すると、Windows の標準に合わせて OLE ドキュメント アイテムのプロパティを簡単に表示および変更できます。 これらのプロパティには、ドキュメント アイテムで表されるファイルに関する情報、アイコンとイメージの拡大縮小を表示するためのオプション、アイテムのリンクに関する情報 (アイテムがリンクされている場合) などがあります。

オブジェクトを`COlePropertiesDialog`使用するには、まずコンストラクタを使用してオブジェクト`COlePropertiesDialog`を作成します。 ダイアログ ボックスが作成されたら、メンバー関数を`DoModal`呼び出してダイアログ ボックスを表示し、ユーザーがアイテムのプロパティを変更できるようにします。 `DoModal`は、ユーザーが OK (IDOK) またはキャンセル (IDCANCEL) ボタンを選択したかどうかを返します。 [OK] ボタンと [キャンセル] ボタンに加えて、[適用] ボタンもあります。 ユーザーが [適用] を選択すると、ドキュメント アイテムのプロパティに加えた変更がアイテムに適用され、そのイメージは自動的に更新されますが、アクティブなままになります。

[m_psh](#m_psh)データ メンバーは`PROPSHEETHEADER`構造体へのポインターであり、ほとんどの場合、明示的にアクセスする必要はありません。 1 つの例外は、既定の [全般]、[表示]、および [リンク] ページ以外の追加のプロパティ ページが必要な場合です。 この場合、メンバー関数を`m_psh`呼び出す前に、カスタム ページを含`DoModal`むようにデータ メンバーを変更できます。

OLE ダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

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

## <a name="colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a>ダイアログ ボックス::プロパティダイアログ

`COlePropertiesDialog` オブジェクトを作成します。

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
プロパティがアクセスされているドキュメント アイテムへのポインター。

*nスケールミン*<br/>
ドキュメント アイテムのイメージの最小スケーリング率。

*nスケールマックス*<br/>
ドキュメント アイテムのイメージの最大スケーリング率。

*pParentWnd*<br/>
ダイアログ ボックスの親または所有者へのポインター。

### <a name="remarks"></a>解説

ドキュメント アイテムのスケーリングを実装するために、`COlePropertiesDialog`共通の OLE オブジェクト プロパティ ダイアログ クラスをから派生します。 このクラスのインスタンスによって実装されるダイアログ ボックスは、ドキュメント アイテムのスケーリングをサポートしません。

既定では、[OLE オブジェクトのプロパティ] ダイアログ ボックスには、既定の 3 つのページがあります。

- 全般

   このページには、選択したドキュメントアイテムで表されるファイルのシステム情報が含まれています。 このページから、ユーザーは選択した項目を別の種類に変換できます。

- 表示

   このページには、項目の表示、アイコンの変更、およびイメージの拡大縮小の変更を行うためのオプションが含まれています。

- Link

   このページには、リンクアイテムの場所を変更するオプションと、リンクアイテムを更新するためのオプションがあります。 このページから、選択した項目のリンクを解除できます。

既定で提供されているページ以外のページを追加するには[m_psh](#m_psh)、派生クラスのコンストラクターを終了する前に`COlePropertiesDialog`m_pshメンバー変数を変更します。 これは`COlePropertiesDialog`、コンストラクターの高度な実装です。

## <a name="colepropertiesdialogdomodal"></a><a name="domodal"></a>ダイアログ ボックス::Do モーダル

このメンバー関数を呼び出すと、Windows の共通の OLE オブジェクト プロパティ ダイアログ ボックスが表示され、ユーザーはドキュメント アイテムのさまざまなプロパティを表示したり、変更したりできます。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

成功した場合は IDOK または IDCANCEL。それ以外の場合は 0。 IDOK と IDCANCEL は、ユーザーが [OK] または [キャンセル] ボタンを選択したかどうかを示す定数です。

IDCANCEL が返された場合は[、エラーが](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror)発生したかどうかを判断する関数を呼び出すことができます。

## <a name="colepropertiesdialogm_gp"></a><a name="m_gp"></a>ダイアログ::m_gp

OLE オブジェクトのプロパティ ダイアログ ボックスの全般ページを初期化するために使用される[OLEUIGNRLPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuignrlpropsw)型の構造体。

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>解説

このページには埋め込みの種類とサイズが表示され、ユーザーは [変換] ダイアログ ボックスにアクセスできます。 このページには、オブジェクトがリンクの場合のリンク先も表示されます。

構造の`OLEUIGNRLPROPS`詳細については、Windows SDK を参照してください。

## <a name="colepropertiesdialogm_lp"></a><a name="m_lp"></a>ダイアログ::m_lp

OLE オブジェクトのプロパティ ダイアログ ボックスのリンク ページを初期化するために使用される[OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw)型の構造体。

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>解説

このページには、リンクされたアイテムの場所が表示され、ユーザーはアイテムへのリンクを更新または解除できます。

構造の`OLEUILINKPROPS`詳細については、Windows SDK を参照してください。

## <a name="colepropertiesdialogm_op"></a><a name="m_op"></a>ダイアログ::m_op

[OLEUIOBJECTPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiobjectpropsw)型の構造体で、共通の OLE オブジェクト プロパティ ダイアログ ボックスを初期化するために使用します。

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>解説

この構造体には、全般、リンク、およびビューの各ページを初期化するために使用されるメンバーが含まれています。

詳細については、Windows SDK の「OLEUI オブジェクトの割り当てと[OLEUILINKPROPS」](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw)を参照してください。

## <a name="colepropertiesdialogm_psh"></a><a name="m_psh"></a>ダイアログ::m_psh

メンバーがダイアログ オブジェクトの特性を格納する型[の構造体](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)。

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>解説

オブジェクトを`COlePropertiesDialog`作成した後、メンバー関数`m_psh`を呼び出す前にダイアログ ボックスのさまざまな側面`DoModal`を設定できます。

データ メンバーを`m_psh`直接変更すると、既定の動作がオーバーライドされます。

構造の`PROPSHEETHEADER`詳細については、Windows SDK を参照してください。

## <a name="colepropertiesdialogm_vp"></a><a name="m_vp"></a>プロパティダイアログ::m_vp

OLE オブジェクトのプロパティ ダイアログ ボックスの [ビュー] ページを初期化するために使用される[OLEUIVIEWPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiviewpropsw)型の構造体。

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>解説

このページでは、オブジェクトの"コンテンツ"ビューと"アイコニック"ビューを切り替えることができ、コンテナ内でのスケーリングを変更できます。 また、オブジェクトがアイコンとして表示されているときに、ユーザーが [アイコンの変更] ダイアログ ボックスにアクセスすることもできます。

構造の`OLEUIVIEWPROPS`詳細については、Windows SDK を参照してください。

## <a name="colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a>コントロールプロパティダイアログ::オンApplyスケール

スケーリング値が変更され、[OK] または [適用] が選択されたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
プロパティがアクセスされているドキュメント アイテムへのポインター。

*nカレントスケール*<br/>
ダイアログ スケールの数値。

*bRelativeToOrig*<br/>
ドキュメント アイテムの元のサイズにスケーリングを適用するかどうかを示します。

### <a name="return-value"></a>戻り値

処理された場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

既定の実装では、何も行われません。 スケーリング コントロールを有効にするには、この関数をオーバーライドする必要があります。

> [!NOTE]
> 共通の OLE オブジェクト プロパティ ダイアログ ボックスが表示される前に、フレームワークは *、pItem*の場合は*NULL、nCurrentScale*の場合は - 1 でこの関数を呼び出します。 これは、スケーリングコントロールを有効にするかどうかを決定するために行われます。

## <a name="see-also"></a>関連項目

[MFC サンプル CIRC](../../overview/visual-cpp-samples.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[CPropertyPage クラス](../../mfc/reference/cpropertypage-class.md)
