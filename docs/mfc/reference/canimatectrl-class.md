---
title: CAnimateCtrl クラス
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
ms.openlocfilehash: 8c8a6d3e83534cd5670e43a9009b8919a2e57f92
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281374"
---
# <a name="canimatectrl-class"></a>CAnimateCtrl クラス

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
|[CAnimateCtrl::Close](#close)|AVI クリップを閉じます。|
|[CAnimateCtrl::Create](#create)|アニメーション コントロールを作成し、それにアタッチ、`CAnimateCtrl`オブジェクト。|
|[CAnimateCtrl::CreateEx](#createex)|指定した Windows の拡張スタイルを使用してアニメーション コントロールを作成しにアタッチします、`CAnimateCtrl`オブジェクト。|
|[CAnimateCtrl::IsPlaying](#isplaying)|Audio-video Interleaved (AVI)、クリップを再生するかどうかを示します。|
|[CAnimateCtrl::Open](#open)|ファイルまたはリソースから、AVI クリップを開き、最初のフレームを表示します。|
|[CAnimateCtrl::Play](#play)|サウンドなし AVI クリップを再生します。|
|[CAnimateCtrl::Seek](#seek)|AVI クリップの選択した 1 つのフレームが表示されます。|
|[CAnimateCtrl::Stop](#stop)|AVI クリップの再生を停止します。|

## <a name="remarks"></a>Remarks

このコントロール (つまり、`CAnimateCtrl`クラス) は以降、Windows 95、Windows 98、および Windows NT version 3.51 で実行するプログラムにのみ使用できます。

アニメーション コントロールは、AVI (オーディオ Video Interleaved) 形式でクリップを表示する四角形のウィンドウ: 標準の Windows ビデオ/オーディオ形式。 AVI クリップは、一連の映画のように、ビットマップ フレームです。

アニメーション コントロールは、単純な AVI クリップのみを再生できます。 具体的には、アニメーション コントロールで再生するクリップは、次の要件を満たす必要があります。

- ビデオ ストリームを 1 つだけ必要があるし、少なくとも 1 つのフレームが必要になります。

- 最大で 2 つのストリームにできますファイル (通常、その他のストリーム存在する場合は、オーディオ ストリーム アニメーション コントロール オーディオ情報を無視しますが)。

- クリップは現在必要がありますか、圧縮されていない、または RLE8 圧縮で圧縮されます。

- ビデオ ストリームでは、パレットの変更は許可されません。

AVI クリップを追加するには、AVI リソースとしてアプリケーションに、または別の AVI ファイルとしてアプリケーションを伴うことができます。

スレッドの継続実行 AVI クリップが表示されますが、ために、アニメーション コントロールの 1 つの一般的な用途は、時間のかかる操作中にシステムの使用状況を示すは。 たとえば、ファイル エクスプ ローラーの検索 ダイアログ ボックスでは、システム ファイルを検索として移動虫眼鏡が表示されます。

作成する場合、`CAnimateCtrl`ボックスまたはダイアログ エディターを使用して、ダイアログ リソースから自動的に破棄されます ダイアログ ボックスを閉じると、ダイアログ ボックスでオブジェクトします。

作成する場合、`CAnimateCtrl`オブジェクト、ウィンドウ内にそれを破棄する必要があります。 作成する場合、`CAnimateCtrl`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CAnimateCtrl`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を破棄するオブジェクト。 新しいクラスを派生させる場合`CAnimateCtrl`とそのクラスのメモリを割り当てることをオーバーライド、`CAnimateCtrl`デストラクターの割り当てを破棄します。

使用しての詳細については`CAnimateCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CAnimateCtrl](../../mfc/using-canimatectrl.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CAnimateCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

##  <a name="canimatectrl"></a>  CAnimateCtrl::CAnimateCtrl

`CAnimateCtrl` オブジェクトを構築します。

```
CAnimateCtrl();
```

### <a name="remarks"></a>Remarks

呼び出す必要があります、[作成](#create)メンバー関数を作成するオブジェクトの他の操作を実行する前にします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]

##  <a name="close"></a>  CAnimateCtrl::Close

アニメーション コントロール (存在する場合) で既に開かれている AVI クリップを閉じてメモリから削除されます。

```
BOOL Close();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  例をご覧ください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。

##  <a name="create"></a>  CAnimateCtrl::Create

アニメーション コントロールを作成し、それにアタッチ、`CAnimateCtrl`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
アニメーション コントロールのスタイルを指定します。 以下の「解説」セクションとアニメーション コントロールのスタイルで説明されているスタイルが説明されている windows 任意組み合わせを適用[アニメーション コントロールのスタイル](/windows/desktop/Controls/animation-control-styles)Windows SDK に含まれています。

*rect*<br/>
アニメーション コントロールの位置とサイズを指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/desktop/api/windef/ns-windef-tagrect)構造体。

*pParentWnd*<br/>
アニメーション コントロールの親ウィンドウを通常を指定します、`CDialog`します。 NULL は指定できません。

*nID*<br/>
アニメーション コントロールの ID を指定します

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築する、`CAnimateCtrl`で 2 つの手順。 最初に、コンス トラクターを呼び出してを呼び出して`Create`、アニメーション コントロールを作成しにアタッチする`CAnimateCtrl`オブジェクト。

次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)アニメーション コントロールにします。

- WS_CHILD 常に

- WS_VISIBLE 通常

- WS_DISABLED ことはほとんどありません。

アニメーション コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに`Create`します。

上記のウィンドウ スタイル、だけでなくアニメーション コントロールに 1 つまたは複数のアニメーション コントロールのスタイルを適用します。 詳細については、Windows SDK を参照してください[アニメーション コントロールのスタイル](/windows/desktop/Controls/animation-control-styles)します。

### <a name="example"></a>例

  例をご覧ください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。

##  <a name="createex"></a>  CAnimateCtrl::CreateEx

コントロール (子ウィンドウ) を作成しに関連付けます、`CAnimateCtrl`オブジェクト。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
作成されるコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK に含まれています。

*dwStyle*<br/>
アニメーション コントロールのスタイルを指定します。 ウィンドウの任意の組み合わせを適用し、で説明されているアニメーション コントロールのスタイル[アニメーション コントロールのスタイル](/windows/desktop/Controls/animation-control-styles)Windows SDK に含まれています。

*rect*<br/>
参照を[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

使用`CreateEx`の代わりに[作成](#create)、Windows の拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。

##  <a name="isplaying"></a>  CAnimateCtrl::IsPlaying

Audio-video Interleaved (AVI)、クリップを再生するかどうかを示します。

```
BOOL IsPlaying() const;
```

### <a name="return-value"></a>戻り値

AVI クリップが再生中以外の場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [ACM_ISPLAYING](/windows/desktop/Controls/acm-isplaying)メッセージは、Windows SDK で説明します。

##  <a name="open"></a>  CAnimateCtrl::Open

AVI クリップを開くし、最初のフレームを表示するには、この関数を呼び出します。

```
BOOL Open(LPCTSTR lpszFileName);
BOOL Open(UINT nID);
```

### <a name="parameters"></a>パラメーター

*lpszFileName*<br/>
A`CString`オブジェクトまたは AVI ファイルの名前または AVI リソースの名前を含む null で終わる文字列へのポインター。 このパラメーターが NULL の場合、システムは、存在する場合、アニメーション コントロールの既に開かれている AVI クリップを閉じます。

*nID*<br/>
AVI リソース識別子です。 このパラメーターが NULL の場合、システムは、存在する場合、アニメーション コントロールの既に開かれている AVI クリップを閉じます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

AVI リソースは、アニメーション コントロールを作成したモジュールから読み込まれます。

`Open` AVI クリップ; でサウンドをサポートしていませんサイレント AVI クリップのみを開くことができます。

アニメーション コントロールが、`ACS_AUTOPLAY`スタイル、アニメーション コントロールは自動的に開始が作成され後すぐにクリップを再生します。 スレッドの継続の実行中に、バック グラウンドでクリップを再生を続けます。 クリップが完了すると、再生が自動的に繰り返されます。

アニメーション コントロールが、`ACS_CENTER`スタイル、AVI クリップがコントロールの中央、およびコントロールのサイズは変更されません。 アニメーション コントロールがない場合、`ACS_CENTER`スタイル、AVI クリップ内のイメージのサイズに AVI クリップが開かれたときに、コントロールがサイズ変更されます。 コントロールの左上隅の位置は変更されません、コントロールのサイズのみ。

アニメーション コントロールが、 `ACS_TRANSPARENT` 、透明な背景を使用して最初のフレームが描画されるのではなくスタイルで背景色が指定された、アニメーション クリップします。

### <a name="example"></a>例

  例をご覧ください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。

##  <a name="play"></a>  CAnimateCtrl::Play

アニメーション コントロールで AVI クリップを再生するには、この関数を呼び出します。

```
BOOL Play(
    UINT nFrom,
    UINT nTo,
    UINT nRep);
```

### <a name="parameters"></a>パラメーター

*nFrom*<br/>
再生を開始するフレームの 0 から始まるインデックス。 値は、65,536 未満である必要があります。 値 0 AVI クリップの最初のフレームを始めることを意味します。

*フォーム状態*<br/>
0 から始まるインデックス、フレームの再生を終了します。 値は、65,536 未満である必要があります。 値 - 1 は、AVI クリップの最後のフレームの終了を意味します。

*nRep*<br/>
AVI クリップを再生する時間数。 値 - 1 は、ファイルの再生を無期限にするかを意味します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

アニメーション コントロールが、スレッドの継続の実行中には、バック グラウンドでクリップを再生します。 アニメーション コントロールが`ACS_TRANSPARENT`スタイル、AVI クリップに再生するアニメーション クリップに指定された背景色ではなく、透明な背景を使用します。

### <a name="example"></a>例

  例をご覧ください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。

##  <a name="seek"></a>  CAnimateCtrl::Seek

静的に AVI クリップの 1 つのフレームを表示するには、この関数を呼び出します。

```
BOOL Seek(UINT nTo);
```

### <a name="parameters"></a>パラメーター

*フォーム状態*<br/>
表示するフレームの 0 から始まるインデックス。 値は、65,536 未満である必要があります。 値が 0 の手段が AVI クリップの最初のフレームを表示します。 値が-1 の手段が AVI クリップの最後のフレームを表示します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

アニメーション コントロールが`ACS_TRANSPARENT`、透明な背景を使用して、AVI クリップが描画されるのではなくスタイルで背景色が指定された、アニメーション クリップします。

### <a name="example"></a>例

  例をご覧ください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。

##  <a name="stop"></a>  CAnimateCtrl::Stop

アニメーション コントロールで AVI クリップの再生を停止するには、この関数を呼び出します。

```
BOOL Stop();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  例をご覧ください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAnimateCtrl::Create](#create)<br/>
[ON_CONTROL](message-map-macros-mfc.md#on_control)
