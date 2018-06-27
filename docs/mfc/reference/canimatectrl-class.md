---
title: CAnimateCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48c431ecbcc415776ff9accfb68004c7c8e46d34
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952327"
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
|[CAnimateCtrl::CreateEx](#createex)|指定された Windows 拡張スタイルでアニメーション コントロールを作成しにアタッチ、`CAnimateCtrl`オブジェクト。|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Audio-video Interleaved (AVI) クリップを再生するかどうかを示します。|  
|[CAnimateCtrl::Open](#open)|ファイルまたはリソースから AVI クリップを開き、最初のフレームを表示します。|  
|[CAnimateCtrl::Play](#play)|サウンドなし AVI クリップを再生します。|  
|[CAnimateCtrl::Seek](#seek)|AVI クリップの選択した 1 つのフレームを表示します。|  
|[CAnimateCtrl::Stop](#stop)|AVI クリップの再生を停止します。|  
  
## <a name="remarks"></a>Remarks  
 このコントロール (したがって、`CAnimateCtrl`クラス) は、Windows 95、Windows 98、および Windows NT 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 アニメーション コントロール AVI (オーディオ Video Interleaved) 形式でクリップを表示する方形ウィンドウは、-、標準の Windows ビデオ/オーディオ形式です。 AVI クリップは、一連の映画のように、ビットマップ フレームです。  
  
 アニメーション コントロールは、単純な AVI クリップのみを再生できます。 具体的には、アニメーション コントロールで再生するクリップは、次の要件を満たす必要があります。  
  
-   1 つのビデオ ストリームである必要がありますされ、少なくとも 1 つのフレームが必要です。  
  
-   最大で 2 つのストリームにできますファイル (通常、その他のストリーム存在する場合がオーディオ ストリーム、アニメーション コントロールのオーディオ情報は無視されます)。  
  
-   クリップは現在必要がありますか、圧縮されていない、または RLE8 の圧縮で圧縮します。  
  
-   ビデオ ストリームでは、パレットの変更は許可されません。  
  
 AVI クリップを追加するには、AVI リソースとしてアプリケーションにまたは別の AVI ファイルとして、アプリケーションを伴うことができます。  
  
 スレッドは、AVI クリップが表示されている間の実行を続行、ためアニメーション コントロールの 1 つの一般的な用途は、時間のかかる操作中にシステムの利用状況を示すです。 たとえば、ファイル エクスプ ローラーの検索 ダイアログ ボックスでは、として、システム ファイルを検索します間、虫眼鏡を表示します。  
  
 作成する場合、`CAnimateCtrl`ボックスまたはダイアログ エディターを使用して、ダイアログ リソースから自動的に破棄されます ダイアログ ボックスを閉じたときに、ダイアログ ボックスでオブジェクトします。  
  
 作成する場合、`CAnimateCtrl`ウィンドウ内でオブジェクトを破棄する必要があります。 作成する場合、`CAnimateCtrl`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CAnimateCtrl`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を破棄するオブジェクト。 新しいクラスを派生する場合`CAnimateCtrl`とそのクラスのメモリの割り当て、オーバーライド、`CAnimateCtrl`デストラクターが、割り当てを破棄します。  
  
 使用する方法について`CAnimateCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CAnimateCtrl](../../mfc/using-canimatectrl.md)です。  
  
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
 呼び出す必要があります、[作成](#create)メンバー関数を作成するオブジェクトで他の操作を実行する前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="close"></a>  CAnimateCtrl::Close  
 アニメーション コントロール (存在する場合) で既に開かれている AVI クリップを閉じて、メモリから削除されます。  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照して[CAnimateCtrl::CAnimateCtrl](#canimatectrl)です。  
  
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
 *dwStyle*  
 アニメーション コントロールのスタイルを指定します。 以下の「解説」セクションとアニメーション コントロールのスタイルで説明されているスタイルが説明されている windows 任意組み合わせを適用[アニメーション コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761886)Windows SDK に含まれています。  
  
 *rect*  
 アニメーション コントロールの位置とサイズを指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 *pParentWnd*  
 アニメーション コントロールの親ウィンドウを通常を指定します、`CDialog`です。 なければなりません**NULL**です。  
  
 *nID*  
 アニメーション コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CAnimateCtrl` 2 つの手順でします。 最初に、コンス トラクターを呼び出しておよびを呼び出す`Create`、アニメーション コントロールを作成しにアタッチする、`CAnimateCtrl`オブジェクト。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)アニメーション コントロールにします。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
 アニメーション コントロールと共に拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに`Create`です。  
  
 上に示したウィンドウ スタイルに加え、アニメーション コントロールに 1 つ以上のアニメーション コントロールのスタイルを適用します。 詳細については、Windows SDK を参照してください[アニメーション コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761886)です。  
  
### <a name="example"></a>例  
  例を参照して[CAnimateCtrl::CAnimateCtrl](#canimatectrl)です。  
  
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
 *dwExStyle*  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 *dwStyle*  
 アニメーション コントロールのスタイルを指定します。 ウィンドウの任意の組み合わせを適用し、で説明したアニメーション コントロールのスタイル[アニメーション コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761886)Windows SDK に含まれています。  
  
 *rect*  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体*pParentWnd*です。  
  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *nID*  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用して`CreateEx`の代わりに[作成](#create)Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
##  <a name="isplaying"></a>  CAnimateCtrl::IsPlaying  
 Audio-video Interleaved (AVI) クリップを再生するかどうかを示します。  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `true` AVI クリップが再生中以外の場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895) Windows SDK で説明するメッセージ。  
  
##  <a name="open"></a>  CAnimateCtrl::Open  
 AVI クリップを開き、最初のフレームを表示するには、この関数を呼び出します。  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *場合*  
 A`CString`オブジェクトまたは AVI ファイルの名前または AVI リソースの名前を表す null で終わる文字列へのポインター。 このパラメーターが場合**NULL**システムが存在する場合、アニメーション コントロールは、既に開かれている AVI クリップを閉じます。  
  
 *nID*  
 AVI リソースの識別子。 このパラメーターが場合**NULL**システムが存在する場合、アニメーション コントロールは、既に開かれている AVI クリップを閉じます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 アニメーション コントロールを作成したモジュールから、AVI リソースが読み込まれます。  
  
 **開く**AVI クリップ; でサウンドをサポートしていませんサイレント AVI クリップのみを開くことができます。  
  
 アニメーション コントロールが、`ACS_AUTOPLAY`スタイル、アニメーション コントロールが自動的に起動が作成され後すぐにクリップを再生します。 スレッドの実行を続行中は、バック グラウンドでクリップを再生続行されます。 クリップが完了すると、再生中には自動的に繰り返されます。  
  
 アニメーション コントロールが、 `ACS_CENTER` AVI クリップがコントロールの中央とスタイル、およびコントロールのサイズは変更されません。 アニメーション コントロールがない場合、`ACS_CENTER`スタイル、AVI クリップが AVI クリップの画像のサイズに開かれたときに、コントロールがサイズ変更されます。 コントロールの左上隅の位置は変更されません、コントロールのサイズのみ。  
  
 アニメーション コントロールが、 `ACS_TRANSPARENT` 、透明な背景を使用して最初のフレームが描画されるのではなくスタイルで指定された背景色、アニメーション クリップします。  
  
### <a name="example"></a>例  
  例を参照して[CAnimateCtrl::CAnimateCtrl](#canimatectrl)です。  
  
##  <a name="play"></a>  CAnimateCtrl::Play  
 アニメーション コントロールで AVI クリップを再生するには、この関数を呼び出します。  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>パラメーター  
 *nFrom*  
 再生を開始するフレームの 0 から始まるインデックス。 値は、65,536 未満にする必要があります。 手段が AVI クリップの最初のフレームで始まる 0 の値です。  
  
 *フォーム状態*  
 フレームの 0 から始まるインデックスで再生を終了します。 値は、65,536 未満にする必要があります。 値 1 は、AVI クリップ内の最後のフレームで終わることを意味します。  
  
 *nRep*  
 AVI クリップを再生する回数です。 値 - 1 では、ファイルを無期限に再生を意味します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 アニメーション コントロールが、スレッドの継続の実行中には、バック グラウンドでクリップを再生します。 アニメーション コントロールが`ACS_TRANSPARENT`スタイル、AVI クリップに再生するアニメーションのクリップに指定された背景色ではなく、透明な背景を使用します。  
  
### <a name="example"></a>例  
  例を参照して[CAnimateCtrl::CAnimateCtrl](#canimatectrl)です。  
  
##  <a name="seek"></a>  CAnimateCtrl::Seek  
 静的に AVI クリップの 1 つのフレームを表示するには、この関数を呼び出します。  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>パラメーター  
 *フォーム状態*  
 表示するフレームの 0 から始まるインデックス。 値は、65,536 未満にする必要があります。 値が 0 の手段が AVI クリップの最初のフレームを表示します。 値が-1 の手段が AVI クリップの最後のフレームを表示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 アニメーション コントロールが`ACS_TRANSPARENT`、透明な背景を使用して、AVI クリップが描画されるのではなくスタイルで指定された背景色、アニメーション クリップします。  
  
### <a name="example"></a>例  
  例を参照して[CAnimateCtrl::CAnimateCtrl](#canimatectrl)です。  
  
##  <a name="stop"></a>  CAnimateCtrl::Stop  
 アニメーション コントロールでの AVI クリップの再生を停止するには、この関数を呼び出します。  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照して[CAnimateCtrl::CAnimateCtrl](#canimatectrl)です。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](message-map-macros-mfc.md#on_control)

