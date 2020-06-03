---
title: クラスを設定します。
ms.date: 11/04/2016
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
ms.openlocfilehash: 3664149ef0d7476b460ef06cddaf2b8145ade701
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753690"
---
# <a name="cpagesetupdialog-class"></a>クラスを設定します。

印刷マージンの設定や変更の追加サポートと共に [OLE ページの設定] ダイアログ ボックスにより提供されるサービスをカプセル化します。

## <a name="syntax"></a>構文

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ページ設定ダイアログ::ページ設定ダイアログ](#cpagesetupdialog)|`CPageSetupDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ページ設定ダイアログ::プリンタDCの作成](#createprinterdc)|印刷用のデバイス コンテキストを作成します。|
|[ページ設定ダイアログ::Doモーダル](#domodal)|ダイアログ ボックスを表示し、ユーザーが選択できるようにします。|
|[ページ設定ダイアログ::デバイス名を取得します。](#getdevicename)|プリンタのデバイス名を返します。|
|[ページ設定ダイアログ::GetDevモード](#getdevmode)|プリンタの現在の DEVMODE を返します。|
|[ページ設定ダイアログ::ドライバー名を取得します。](#getdrivername)|プリンタで使用されているドライバを返します。|
|[ページ設定ダイアログ::取得マージン](#getmargins)|プリンタの現在の余白設定を返します。|
|[ページ設定ダイアログ::用紙サイズを取得します。](#getpapersize)|プリンタの用紙サイズを返します。|
|[ページ設定ダイアログ::ポート名を取得します。](#getportname)|出力ポート名を返します。|
|[ページ設定ダイアログ::ページ上](#ondrawpage)|印刷ページの画面イメージをレンダリングするために、フレームワークによって呼び出されます。|
|[ページ設定ダイアログ::P再描画ページ](#predrawpage)|印刷ページの画面イメージをレンダリングする前に、フレームワークによって呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ページ設定ダイアログ::m_psd](#m_psd)|オブジェクトをカスタマイズするために使用する`CPageSetupDialog`構造体。|

## <a name="remarks"></a>解説

このクラスは、[印刷設定] ダイアログ ボックスの代わりに使用されます。

オブジェクトを`CPageSetupDialog`使用するには、まずコンストラクタを使用してオブジェクト`CPageSetupDialog`を作成します。 ダイアログ ボックスが作成されたら、データ メンバーの値を`m_psd`設定または変更して、ダイアログ ボックスのコントロールの値を初期化できます。 [m_psd](#m_psd)構造は、タイプが PAGESETUPDLG です。

ダイアログ ボックス コントロールを初期化した後、`DoModal`メンバー関数を呼び出してダイアログ ボックスを表示し、ユーザーが印刷オプションを選択できるようにします。 `DoModal`は、ユーザーが OK (IDOK) ボタンまたはキャンセル (IDCANCEL) ボタンを選択したかどうかを返します。

IDOK を返す場合`DoModal`は、いくつかの`CPageSetupDialog`メンバー関数を使用するか、`m_psd`データ メンバーにアクセスして、ユーザーが入力した情報を取得できます。

> [!NOTE]
> [OLE ページ設定] ダイアログ ボックスを一時閉じた後、ユーザーが行った変更はフレームワークによって保存されません。 このダイアログ ボックスから、アプリケーションのドキュメント クラスやアプリケーション クラスのメンバーなどの永続的な場所に値を保存するのは、アプリケーション自体の必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="cpagesetupdialogcpagesetupdialog"></a><a name="cpagesetupdialog"></a>ページ設定ダイアログ::ページ設定ダイアログ

`CPageSetupDialog`オブジェクトを構築します。

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ダイアログ ボックスの設定をカスタマイズするために使用できる 1 つ以上のフラグ。 値はビットごとの OR 演算子を使用して組み合わせることができます。 これらの値には次の意味があります。

- PSD_DEFAULTMINMARGINS 用紙の余白の最小許容幅をプリンターの最小値と同じに設定します。 このフラグは、PSD_MARGINS フラグと PSD_MINMARGINS フラグも指定されている場合は無視されます。

- PSD_INWININIINTLMEASURE 実装されていません。

- PSD_MINMARGINS`rtMinMargin`メンバーに指定された値を、左、上、右、および下の余白の最小許容幅として使用します。 システムは、ユーザーが指定された最小値より小さい幅を入力できないようにします。 PSD_MINMARGINSを指定しない場合、プリンタで許可される最小幅がシステムによって設定されます。

- PSD_MARGINS マージン制御領域をアクティブにします。

- PSD_INTHOUSANDTHSOFINCHES ダイアログ ボックスの単位を 1/1000 インチ単位で計測します。

- PSD_INHUNDREDTHSOFMILLIMETERS ダイアログ ボックスの単位を 1/100 ミリメートル単位で測定します。

- PSD_DISABLEMARGINS 余白ダイアログ ボックス コントロールを無効にします。

- PSD_DISABLEPRINTER プリンターボタンを無効にします。

- PSD_NOWARNING 既定のプリンタがない場合に警告メッセージが表示されないようにします。

- PSD_DISABLEORIENTATION ページ方向ダイアログ コントロールを無効にします。

- PSD_RETURNDEFAULT`CPageSetupDialog`ダイアログ ボックスを表示せずにシステムの既定のプリンターで初期化された[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体および[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)構造体を返します。 両方とも`hDevNames`NULL`hDevMode`であると想定されます。それ以外の場合、関数はエラーを返します。 システムのデフォルトプリンタが古いプリンタ ドライバ (Windows Version 3.0 より前`hDevNames`) でサポートされている場合は、返されるのは、プリンタドライバだけです。`hDevMode`は NULL です。

- PSD_DISABLEPAPER用紙選択コントロールを無効にします。

- PSD_SHOWHELP ダイアログ ボックスに [ヘルプ] ボタンが表示されます。 この`hwndOwner`フラグが指定されている場合、メンバーは NULL であってはなりません。

- PSD_ENABLEPAGESETUPHOOK で指定されたフック関数`lpfnSetupHook`を有効にします。

- PSD_ENABLEPAGESETUPTEMPLATE で識別されるダイアログ テンプレート ボックスを使用して、オペレーティング システムが`hInstance`ダイアログ`lpSetupTemplateName`ボックスを作成します。

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE事前に`hInstance`読み込まれたダイアログ ボックス テンプレートを含むデータ ブロックを識別することを示します。 このフラグが`lpSetupTemplateName`指定されている場合、システムは無視されます。

- PSD_ENABLEPAGEPAINTHOOK で指定されたフック関数`lpfnPagePaintHook`を有効にします。

- PSD_DISABLEPAGEPAINTING ダイアログ ボックスの描画領域を無効にします。

*pParentWnd*<br/>
ダイアログ ボックスの親または所有者へのポインター。

### <a name="remarks"></a>解説

ダイアログ ボックスを表示するには[、DoModal](../../mfc/reference/cdialog-class.md#domodal)関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

## <a name="cpagesetupdialogcreateprinterdc"></a><a name="createprinterdc"></a>ページ設定ダイアログ::プリンタDCの作成

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体と[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)構造体からプリンター デバイス コンテキストを作成します。

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>戻り値

新しく作成されたプリンター デバイス コンテキスト (DC) へのハンドル。

## <a name="cpagesetupdialogdomodal"></a><a name="domodal"></a>ページ設定ダイアログ::Doモーダル

この関数を呼び出すと、Windows の共通の [OLE ページ設定] ダイアログ ボックスが表示され、印刷余白、用紙のサイズと向き、印刷先のプリンタなどのさまざまな印刷設定オプションをユーザーが選択できるようになります。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

IDOK または ID キャンセル。 IDCANCEL が返された場合は、エラーが発生したかどうかを判断するのには関数[を](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror)呼び出します。

IDOK と IDCANCEL は、ユーザーが [OK] または [キャンセル] ボタンを選択したかどうかを示す定数です。

### <a name="remarks"></a>解説

さらに、ユーザーは、ネットワークの場所や選択したプリンタに固有のプロパティなどのプリンタ設定オプションにアクセスできます。

構造のメンバを設定してさまざまな [ページ設定] ダイアログ オプション`m_psd`を初期化する場合は、 を`DoModal`呼び出す前、およびダイアログ オブジェクトの構築後に初期化する必要があります。 を呼`DoModal`び出した後、他のメンバー関数を呼び出して、ユーザーが入力した設定または情報をダイアログ ボックスに取得します。

ユーザーが入力した現在の設定を反映させる場合は[、CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter)に電話をかけてください。 この関数は、オブジェクトから情報`CPageSetupDialog`を取得し、初期化し、適切な属性を持つ新しいプリンター DC を選択します。

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>例

  次の例[を](#cpagesetupdialog)参照してください。

## <a name="cpagesetupdialoggetdevicename"></a><a name="getdevicename"></a>ページ設定ダイアログ::デバイス名を取得します。

現在選択されているプリンタ`DoModal`の名前を取得するには、この関数を呼び出します。

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>戻り値

オブジェクトによって使用される`CPageSetupDialog`デバイス名。

## <a name="cpagesetupdialoggetdevmode"></a><a name="getdevmode"></a>ページ設定ダイアログ::GetDevモード

オブジェクトのプリンターデバイス`DoModal`コンテキストに関する情報を取得する呼び`CPageSetupDialog`出し後に、この関数を呼び出します。

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>戻り値

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)データ構造体には、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 この構造体で使用されるメモリのロックを解除するには、Windows SDK で説明されている Windows[グローバル ロック解除](/windows/win32/api/winbase/nf-winbase-globalunlock)機能を使用する必要があります。

## <a name="cpagesetupdialoggetdrivername"></a><a name="getdrivername"></a>ページ設定ダイアログ::ドライバー名を取得します。

[DoModal を](../../mfc/reference/cprintdialog-class.md#domodal)呼び出した後、この関数を呼び出して、システム定義のプリンター デバイス ドライバーの名前を取得します。

```
CString GetDriverName() const;
```

### <a name="return-value"></a>戻り値

システム`CString`定義のドライバー名を指定します。

### <a name="remarks"></a>解説

によって返`CString`される`GetDriverName`オブジェクトへのポインターを、 `lpszDriverName` [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)の呼び出しの値として使用します。

## <a name="cpagesetupdialoggetmargins"></a><a name="getmargins"></a>ページ設定ダイアログ::取得マージン

プリンター デバイス ドライバーの余白`DoModal`を取得する呼び出しの後に、この関数を呼び出します。

```cpp
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>パラメーター

*マージン*<br/>
現在選択されているプリンタの印刷マージンを記述する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインタです( 1/1000 インチまたは 1/100 mm)。 この四角形に関心がない場合は、このパラメーターに NULL を渡します。

*マージン*<br/>
現在選択されている`RECT`プリンタの`CRect`最小印刷マージンを記述する構造体またはオブジェクトへのポインタです(1/1000 インチまたは1/100 mm)。 この四角形に関心がない場合は、このパラメーターに NULL を渡します。

## <a name="cpagesetupdialoggetpapersize"></a><a name="getpapersize"></a>ページ設定ダイアログ::用紙サイズを取得します。

印刷用に選択した用紙のサイズを取得します。

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>戻り値

印刷用に選択した用紙のサイズ (1/1000 インチまたは 1/100 mm) を含む[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

## <a name="cpagesetupdialoggetportname"></a><a name="getportname"></a>ページ設定ダイアログ::ポート名を取得します。

現在選択されているプリンタ`DoModal`ポートの名前を取得するために呼び出した後、この関数を呼び出します。

```
CString GetPortName() const;
```

### <a name="return-value"></a>戻り値

現在選択されているプリンタ ポートの名前。

## <a name="cpagesetupdialogm_psd"></a><a name="m_psd"></a>ページ設定ダイアログ::m_psd

メンバがダイアログ オブジェクトの特性を格納する、タイプ PAGESETUPDLG の構造体。

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>解説

オブジェクトを`CPageSetupDialog`作成した後、メンバー関数`m_psd`を呼び出す前にダイアログ ボックスのさまざまな側面`DoModal`を設定できます。

データ メンバーを`m_psd`直接変更すると、既定の動作がオーバーライドされます。

[ページセットアップの詳細](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw)については、Windows SDK を参照してください。

次の例[を](#cpagesetupdialog)参照してください。

## <a name="cpagesetupdialogondrawpage"></a><a name="ondrawpage"></a>ページ設定ダイアログ::ページ上

印刷ページの画面イメージを描画するために、フレームワークによって呼び出されます。

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンターデバイス コンテキストへのポインター。

*メッセージ*<br/>
現在描画中のページの領域を示すメッセージを指定します。 以下のいずれかを指定できます。

- WM_PSD_FULLPAGERECT ページ領域全体。

- WM_PSD_MINMARGINRECT 現在の最小マージン。

- WM_PSD_MARGINRECT 現在の余白。

- WM_PSD_GREEKTEXTRECT ページの内容。

- WM_PSD_ENVSTAMPRECT切手表示用に予約されたエリア。

- WM_PSD_YAFULLPAGERECT 差出人住所表現の領域。 この領域は、サンプル ページ領域の端まで拡張されます。

*Lprect*<br/>
作図領域の座標を含む[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

処理される場合はゼロ以外の値。それ以外の場合は 0。

### <a name="remarks"></a>解説

このイメージは、[OLE ページ設定] ダイアログ ボックスの一部として表示されます。 既定の実装では、テキストのページのイメージを描画します。

イメージの特定の領域またはイメージ全体の描画をカスタマイズするには、この関数をオーバーライドします。 これを行うには、switch**ステートメントを**使用して **、nMessage**の値*nMessage*をチェックする case ステートメントを使用します。 たとえば、ページ イメージの内容のレンダリングをカスタマイズするには、次のコード例を使用します。

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

*nMessage*のすべてのケースを処理する必要はありません。 イメージの 1 つのコンポーネント、イメージの複数のコンポーネント、または領域全体を処理するように選択できます。

## <a name="cpagesetupdialogpredrawpage"></a><a name="predrawpage"></a>ページ設定ダイアログ::P再描画ページ

印刷ページの画面イメージを描画する前に、フレームワークによって呼び出されます。

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>パラメーター

*wペーパー*<br/>
用紙サイズを示す値を指定します。 この値は[、DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体の説明にリストされている**DMPAPER_** 値のいずれかです。

*wフラグ*<br/>
用紙または封筒の向き、およびプリンタがドット マトリックスまたは HPPCL (ヒューレット パッカード プリンタ制御言語) デバイスかどうかを示します。 このパラメーターには、次のいずれかの値を指定できます。

- 0x001 ランドスケープモードの用紙(ドットマトリックス)

- 0x003 ランドスケープモードの用紙(HPPCL)

- 0x005 縦モードの用紙 (ドット マトリックス)

- 0x007 縦モードの用紙 (HPPCL)

- 0x00b 横モード(HPPCL)の封筒

- 0x00d 縦モードのエンベロープ (ドットマトリックス)

- 0x019 横モードの封筒 (ドットマトリックス)

- 0x01f 縦モードのエンベロープ (ドットマトリックス)

*pPSD*<br/>
`PAGESETUPDLG` 構造体へのポインター。 [ページセットアップの](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw)詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

処理される場合はゼロ以外の値。それ以外の場合は 0。

### <a name="remarks"></a>解説

イメージの描画をカスタマイズするには、この関数をオーバーライドします。 この関数をオーバーライドして TRUE を返す場合は、イメージ全体を描画する必要があります。 この関数をオーバーライドして FALSE を返した場合、フレームワークによって既定のイメージ全体が描画されます。

## <a name="see-also"></a>関連項目

[MFC サンプル ワードパッド](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
