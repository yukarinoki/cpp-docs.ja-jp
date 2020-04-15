---
title: CアニマテCtrlクラス
ms.date: 11/04/2016
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
ms.openlocfilehash: fcee569659d732c26e274c8ca189042a16f13557
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371069"
---
# <a name="canimatectrl-class"></a>CアニマテCtrlクラス

Windows コモン アニメーション コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CAnimateCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|`CAnimateCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カニマテCtrl::閉じる](#close)|AVI クリップを閉じます。|
|[CAnimateCtrl::作成](#create)|アニメーション コントロールを作成し、`CAnimateCtrl`オブジェクトにアタッチします。|
|[CAnimateCtrl::作成Ex](#createex)|指定した Windows 拡張スタイルを使用してアニメーション コントロールを作成し`CAnimateCtrl`、オブジェクトにアタッチします。|
|[CアニメイトCtrl::イズプレイング](#isplaying)|オーディオ ビデオ インターリーブ (AVI) クリップが再生中かどうかを示します。|
|[カニマテCtrl::オープン](#open)|ファイルまたはリソースから AVI クリップを開き、最初のフレームを表示します。|
|[チャニマテCtrl::Pレイ](#play)|AVI クリップをサウンドなしで再生します。|
|[カニマテCtrl::シーク](#seek)|AVI クリップの選択した単一フレームを表示します。|
|[カニマテCtrl::ストップ](#stop)|AVI クリップの再生を停止します。|

## <a name="remarks"></a>解説

このコントロール (および`CAnimateCtrl`クラス) は、Windows 95、Windows 98、および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

アニメーション コントロールは、クリップを AVI (オーディオ ビデオ インターリーブ) 形式で表示する四角形のウィンドウです。 AVI クリップは、ムービーのような一連のビットマップフレームです。

アニメーション コントロールでは、単純な AVI クリップしか再生できません。 特に、アニメーション コントロールで再生するクリップは、次の要件を満たす必要があります。

- ビデオ ストリームは 1 つだけ存在し、少なくとも 1 つのフレームが必要です。

- ファイルには、2 つのストリームを含めることができます (通常、他のストリームが存在する場合は、オーディオ ストリームですが、アニメーション コントロールはオーディオ情報を無視します)。

- クリップは、RLE8 圧縮で圧縮されていないか、圧縮されている必要があります。

- ビデオストリームではパレットの変更はできません。

AVI クリップは、AVI リソースとしてアプリケーションに追加することも、アプリケーションを別の AVI ファイルとして添付することもできます。

AVI クリップが表示されている間はスレッドの実行が継続されるため、アニメーション コントロールの一般的な用途として、時間のかかる操作中にシステム アクティビティを示します。 たとえば、ファイル エクスプローラの [検索] ダイアログ ボックスには、システムがファイルを検索する際に、移動する虫眼鏡が表示されます。

ダイアログ ボックス内`CAnimateCtrl`またはダイアログ エディターを使用してダイアログ リソースからオブジェクトを作成すると、ユーザーがダイアログ ボックスを閉じると自動的に破棄されます。

ウィンドウ内にオブジェクト`CAnimateCtrl`を作成する場合は、オブジェクトを破棄する必要があります。 スタック上にオブジェクト`CAnimateCtrl`を作成すると、オブジェクトは自動的に破棄されます。 **新しい**関数を`CAnimateCtrl`使用してヒープ上にオブジェクトを作成する場合は、オブジェクトの**delete**を呼び出して破棄する必要があります。 から新しいクラスを派生`CAnimateCtrl`し、そのクラス内のメモリを割り当`CAnimateCtrl`てる場合は、デストラクタをオーバーライドして割り当てを破棄します。

の詳細`CAnimateCtrl`については、「[コントロール](../../mfc/controls-mfc.md)」および[「CAnimateCtrl を使用する](../../mfc/using-canimatectrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CAnimateCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="canimatectrlcanimatectrl"></a><a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl

`CAnimateCtrl` オブジェクトを構築します。

```
CAnimateCtrl();
```

### <a name="remarks"></a>解説

作成するオブジェクトに対して他の操作を実行する前に[、Create](#create)メンバー関数を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]

## <a name="canimatectrlclose"></a><a name="close"></a>カニマテCtrl::閉じる

アニメーション コントロールで以前に開いていた AVI クリップを閉じ、メモリから削除します。

```
BOOL Close();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [「CAnimateCtrl::CAnimateCtrl」](#canimatectrl)の例を参照してください。

## <a name="canimatectrlcreate"></a><a name="create"></a>CAnimateCtrl::作成

アニメーション コントロールを作成し、`CAnimateCtrl`オブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
アニメーション コントロールのスタイルを指定します。 「解説」で説明するウィンドウ スタイルと、Windows SDK のアニメーション コントロール[スタイル](/windows/win32/Controls/animation-control-styles)で説明されているアニメーション コントロール スタイルを任意に組み合わせて適用します。

*Rect*<br/>
アニメーション コントロールの位置とサイズを指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
アニメーション コントロールの親ウィンドウを指定`CDialog`します。 NULL にすることはできません。

*nID*<br/>
アニメーション コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

を`CAnimateCtrl`2 つの手順で作成します。 まず、コンストラクターを呼び出し、`Create`次に`CAnimateCtrl`を呼び出します。

アニメーション コントロールに次の[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を適用します。

- WS_CHILD常に

- WS_VISIBLE通常

- WS_DISABLEDまれ

アニメーション コントロールで拡張ウィンドウ スタイルを使用する場合は、 ではなく[CreateEx](#createex)を`Create`呼び出します。

上記のウィンドウ スタイルに加えて、アニメーション コントロールに 1 つ以上のアニメーション コントロール スタイルを適用することもできます。 [アニメーション コントロール](/windows/win32/Controls/animation-control-styles)スタイルの詳細については、 Windows SDK を参照してください。

### <a name="example"></a>例

  [「CAnimateCtrl::CAnimateCtrl」](#canimatectrl)の例を参照してください。

## <a name="canimatectrlcreateex"></a><a name="createex"></a>CAnimateCtrl::作成Ex

コントロール (子ウィンドウ) を作成し、オブジェクトに関連`CAnimateCtrl`付けます。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*ドウェエクススタイル*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の*DwExStyle*パラメーター[を](/windows/win32/api/winuser/nf-winuser-createwindowexw)参照してください。

*Dwstyle*<br/>
アニメーション コントロールのスタイルを指定します。 Windows SDK のアニメーション コントロール スタイルで説明されているウィンドウと[アニメーション コントロールのスタイル](/windows/win32/Controls/animation-control-styles)を任意に組み合わせて適用します。

*Rect*<br/>
作成するウィンドウのサイズと位置を記述する[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照を *、 pParentWnd*のクライアント座標で指定します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

[`CreateEx`[作成]](#create)の代わりに、Windows 拡張スタイルの序文で指定された拡張 Windows スタイル**を適用WS_EX_。**

## <a name="canimatectrlisplaying"></a><a name="isplaying"></a>CアニメイトCtrl::イズプレイング

オーディオ ビデオ インターリーブ (AVI) クリップが再生中かどうかを示します。

```
BOOL IsPlaying() const;
```

### <a name="return-value"></a>戻り値

AVI クリップが再生されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[ACM_ISPLAYING](/windows/win32/Controls/acm-isplaying)メッセージを送信します。

## <a name="canimatectrlopen"></a><a name="open"></a>カニマテCtrl::オープン

AVI クリップを開き、最初のフレームを表示します。

```
BOOL Open(LPCTSTR lpszFileName);
BOOL Open(UINT nID);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
AVI`CString`ファイルの名前または AVI リソースの名前を含む null で終わる文字列へのオブジェクトまたはポインター。 このパラメータが NULL の場合、アニメーション コントロールで以前に開いていた AVI クリップがある場合は、システムは閉じます。

*nID*<br/>
AVI リソース識別子。 このパラメータが NULL の場合、アニメーション コントロールで以前に開いていた AVI クリップがある場合は、システムは閉じます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アニメーション コントロールを作成したモジュールから AVI リソースが読み込まれます。

`Open`AVI クリップのサウンドはサポートしていません。サイレント AVI クリップのみを開くことができます。

アニメーション コントロールにスタイルが`ACS_AUTOPLAY`設定されている場合、アニメーション コントロールはクリップを開くとすぐに自動的に再生を開始します。 スレッドの実行中も、バックグラウンドでクリップが再生され続けます。 再生が終了すると、自動的に繰り返されます。

アニメーション コントロールにスタイルが`ACS_CENTER`設定されている場合、AVI クリップはコントロールの中央に配置され、コントロールのサイズは変更されません。 アニメーション コントロールに`ACS_CENTER`スタイルがない場合は、AVI クリップを開いたときにコントロールのサイズが変更され、AVI クリップ内のイメージのサイズになります。 コントロールの左上隅の位置は変更されず、コントロールのサイズだけが変わります。

アニメーション コントロールに`ACS_TRANSPARENT`スタイルがある場合、最初のフレームは、アニメーション クリップで指定された背景色ではなく、透明な背景を使用して描画されます。

### <a name="example"></a>例

  [「CAnimateCtrl::CAnimateCtrl」](#canimatectrl)の例を参照してください。

## <a name="canimatectrlplay"></a><a name="play"></a>チャニマテCtrl::Pレイ

アニメーション コントロールで AVI クリップを再生します。

```
BOOL Play(
    UINT nFrom,
    UINT nTo,
    UINT nRep);
```

### <a name="parameters"></a>パラメーター

*nから*<br/>
再生が開始されるフレームの 0 から始まるインデックス。 値は 65,536 未満である必要があります。 値 0 は AVI クリップの最初のフレームから始まります。

*nTo*<br/>
再生が終了するフレームの 0 から始まるインデックス。 値は 65,536 未満である必要があります。 値 -1 は、AVI クリップの最後のフレームで終わりを意味します。

*nRep*<br/>
AVI クリップを再生する回数。 値が - 1 の場合は、ファイルを無期限に再生します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アニメーション コントロールは、スレッドの実行中にバックグラウンドでクリップを再生します。 アニメーション コントロールにスタイル`ACS_TRANSPARENT`がある場合、AVI クリップはアニメーション クリップで指定された背景色ではなく、透明な背景を使用して再生されます。

### <a name="example"></a>例

  [「CAnimateCtrl::CAnimateCtrl」](#canimatectrl)の例を参照してください。

## <a name="canimatectrlseek"></a><a name="seek"></a>カニマテCtrl::シーク

AVI クリップの単一フレームを静的に表示するには、この関数を呼び出します。

```
BOOL Seek(UINT nTo);
```

### <a name="parameters"></a>パラメーター

*nTo*<br/>
表示するフレームの 0 から始まるインデックス。 値は 65,536 未満である必要があります。 値 0 は AVI クリップの最初のフレームを表示します。 値 -1 は AVI クリップの最後のフレームを表示します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アニメーション コントロールにスタイル`ACS_TRANSPARENT`がある場合、AVI クリップはアニメーション クリップで指定された背景色ではなく、透明な背景を使用して描画されます。

### <a name="example"></a>例

[「CAnimateCtrl::CAnimateCtrl」](#canimatectrl)の例を参照してください。

## <a name="canimatectrlstop"></a><a name="stop"></a>カニマテCtrl::ストップ

アニメーション コントロールで AVI クリップの再生を停止します。

```
BOOL Stop();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [「CAnimateCtrl::CAnimateCtrl」](#canimatectrl)の例を参照してください。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CAnimateCtrl::作成](#create)<br/>
[ON_CONTROL](message-map-macros-mfc.md#on_control)
