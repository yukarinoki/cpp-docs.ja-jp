---
title: CPalette クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
dev_langs:
- C++
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36cc13fa77becf5bdeb3960f6ac9db18d5d63dbb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cpalette-class"></a>CPalette クラス
Windows のカラー パレットをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPalette : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPalette::CPalette](#cpalette)|構築、`CPalette`接続されている Windows パレットがないオブジェクトです。 初期化する必要があります、`CPalette`を使用する前に、初期化のメンバー関数のいずれかのオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPalette::AnimatePalette](#animatepalette)|によって識別される論理パレット内のエントリを置き換える、`CPalette`オブジェクト。 Windows システム パレットに新しいエントリをすぐにマップされるので、アプリケーションは、クライアント領域を更新するがありません。|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|デバイス コンテキストのハーフトーン パレットを作成し、それにアタッチ、`CPalette`オブジェクト。|  
|[CPalette::CreatePalette](#createpalette)|Windows のカラー パレットを作成し、それにアタッチ、`CPalette`オブジェクト。|  
|[CPalette::FromHandle](#fromhandle)|ポインターを返します、 `CPalette` Windows パレット オブジェクトへのハンドルが指定されるとします。|  
|[CPalette::GetEntryCount](#getentrycount)|論理パレットのパレット エントリの数を取得します。|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|論理パレットの色の値に最も近い、エントリのインデックスを返します。|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|論理パレットのパレット エントリの範囲を取得します。|  
|[CPalette::ResizePalette](#resizepalette)|指定された論理パレットのサイズを変更、`CPalette`エントリ数の指定したオブジェクト。|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|論理パレット内のエントリの範囲内には、RGB 色の値とフラグを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CPalette::operator HPALETTE](#operator_hpalette)|返します、`HPALETTE`にアタッチされている、`CPalette`です。|  
  
## <a name="remarks"></a>コメント  
 パレットは、アプリケーションと色の出力デバイス (ディスプレイ デバイス) などのインターフェイスを提供します。 インターフェイスは、他のアプリケーションによって表示される色で深刻な干渉することがなくを出力デバイスの色の機能の活用してアプリケーションを使用します。 Windows は、システム パレット (を使用できる色を定義) と、アプリケーションの論理パレット (必要な色の一覧) を使用して、使用する色を決定します。  
  
 A`CPalette`オブジェクトによって参照されるパレットを操作するために、オブジェクトがメンバー関数を提供します。 構築、`CPalette`オブジェクトし、そのメンバー関数を使用して、実際のパレットでは、グラフィックス デバイス インターフェイス (GDI) オブジェクトを作成し、そのエントリとその他のプロパティを操作します。  
  
 使用する方法についての`CPalette`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="animatepalette"></a>  CPalette::AnimatePalette  
 接続されている論理パレット内のエントリを置き換える、`CPalette`オブジェクト。  
  
```  
void AnimatePalette(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartIndex`  
 アニメーション化するには、パレット内の最初のエントリを指定します。  
  
 `nNumEntries`  
 アニメーション化するには、パレット内のエントリの数を指定します。  
  
 `lpPaletteColors`  
 配列の最初のメンバーを指す[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd162769)構造体によって識別されるパレット エントリを置き換える`nStartIndex`と`nNumEntries`です。  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出すと`AnimatePalette`がない、クライアント領域を更新する Windows システム パレットに新しいエントリをすぐにマップされるためです。  
  
 `AnimatePalette`関数が持つエントリを変更するのみ、 **PC_RESERVED**フラグは、対応する設定**palPaletteEntry**のメンバー、[保持](http://msdn.microsoft.com/library/windows/desktop/dd145040)構造体接続されている、`CPalette`オブジェクト。 参照してください**保持**この構造体の詳細については、Windows SDK に含まれています。  
  
##  <a name="cpalette"></a>  CPalette::CPalette  
 `CPalette` オブジェクトを構築します。  
  
```  
CPalette();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを含んでいない添付パレットが呼び出されるまで`CreatePalette`を 1 つをアタッチします。  
  
##  <a name="createhalftonepalette"></a>  CPalette::CreateHalftonePalette  
 デバイス コンテキストのハーフトーン パレットを作成します。  
  
```  
BOOL CreateHalftonePalette(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストの伸縮モードが に設定されているときに、アプリケーションはハーフトーン パレットを作成する必要があります**ハーフトーン**です。 によって返される論理ハーフトーン パレット、 [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503)メンバー関数は、する必要がありますし、選択し、前にデバイス コンテキストに実現、 [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt)または[StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121)関数が呼び出されます。  
  
 詳細については、Windows SDK を参照してください`CreateHalftonePalette`と**StretchDIBits**です。  
  
##  <a name="createpalette"></a>  CPalette::CreatePalette  
 初期化、 `CPalette` Windows 論理カラー パレットを作成してアタッチするオブジェクト、`CPalette`オブジェクト。  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpLogPalette`  
 指す、[保持](http://msdn.microsoft.com/library/windows/desktop/dd145040)論理パレットの色に関する情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、Windows SDK を参照してください、**保持**構造体。  
  
##  <a name="fromhandle"></a>  CPalette::FromHandle  
 ポインターを返します、 `CPalette` Windows パレット オブジェクトへのハンドルが指定されるとします。  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 `hPalette`  
 Windows GDI カラー パレットへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPalette`それ以外の成功した場合は、オブジェクト**NULL**です。  
  
### <a name="remarks"></a>コメント  
 場合、 `CPalette` Windows パレット、一時的なにオブジェクトが既にアタッチされていない`CPalette`オブジェクトが作成され、接続されています。 この一時`CPalette`オブジェクトが有効では、次回アプリケーションがある移動するまでのアイドル時間イベント ループで、すべて一時的なグラフィックを時間でオブジェクトが削除専用です。 つまり、一時オブジェクトは 1 つのウィンドウ メッセージを処理中にのみ有効です。  
  
##  <a name="getentrycount"></a>  CPalette::GetEntryCount  
 指定した論理パレット内のエントリの数を取得するには、このメンバー関数を呼び出します。  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>戻り値  
 論理パレット内のエントリの数です。  
  
##  <a name="getnearestpaletteindex"></a>  CPalette::GetNearestPaletteIndex  
 指定した色の値に最も近い論理パレットのエントリのインデックスを返します。  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 一致する色を指定します。  
  
### <a name="return-value"></a>戻り値  
 論理パレット内のエントリのインデックス。 エントリには、指定された色に最も近い色が含まれています。  
  
##  <a name="getpaletteentries"></a>  CPalette::GetPaletteEntries  
 論理パレットのパレット エントリの範囲を取得します。  
  
```  
UINT GetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartIndex`  
 取得する論理パレットの最初のエントリを指定します。  
  
 `nNumEntries`  
 論理パレットを取得するには、エントリの数を指定します。  
  
 `lpPaletteColors`  
 配列を指す[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd162769)パレット エントリを受信するデータ構造体。 配列で指定された数は、少なくともデータ構造を含める必要があります`nNumEntries`です。  
  
### <a name="return-value"></a>戻り値  
 論理パレット; から取得されたエントリ数関数が失敗した場合は 0 を返します。  
  
##  <a name="operator_hpalette"></a>  CPalette::operator HPALETTE  
 この演算子のアタッチされた Windows GDI ハンドルの取得を使用して、`CPalette`オブジェクト。  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CPalette`オブジェクト。 それ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 この演算子はキャスト演算子の`HPALETTE`オブジェクト。  
  
 グラフィック オブジェクトの使用に関する詳細については、記事を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)Windows SDK に含まれています。  
  
##  <a name="resizepalette"></a>  CPalette::ResizePalette  
 接続されている論理パレットのサイズを変更、`CPalette`オブジェクトで指定されたエントリの数を`nNumEntries`です。  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNumEntries`  
 サイズ変更された後、パレット内のエントリの数を指定します。  
  
### <a name="return-value"></a>戻り値  
 パレットが正しくサイズ変更された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出す場合`ResizePalette`パレットのサイズを減らすためには、サイズ変更されたパレットの残りのエントリは変更されていません。 アプリケーションを呼び出す場合`ResizePalette`パレットを拡大するには、追加のパレット エントリが黒に設定 (赤、緑、青の値はすべて 0)、およびその他のすべてのエントリのフラグが 0 に設定されます。  
  
 Windows API の詳細については`ResizePalette`を参照してください[ため](http://msdn.microsoft.com/library/windows/desktop/dd162928)Windows SDK に含まれています。  
  
##  <a name="setpaletteentries"></a>  CPalette::SetPaletteEntries  
 論理パレット内のエントリの範囲内には、RGB 色の値とフラグを設定します。  
  
```  
UINT SetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartIndex`  
 設定する論理パレットの最初のエントリを指定します。  
  
 `nNumEntries`  
 設定する論理パレット内のエントリの数を指定します。  
  
 `lpPaletteColors`  
 配列を指す[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd162769)パレット エントリを受信するデータ構造体。 配列で指定された数は、少なくともデータ構造を含める必要があります`nNumEntries`です。  
  
### <a name="return-value"></a>戻り値  
 論理パレット内のエントリの数を設定関数が失敗した場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 かどうか、論理パレットが選択されているデバイス コンテキストに、アプリケーションが`SetPaletteEntries`、変更は反映されません、アプリケーションが[:realizepalette](../../mfc/reference/cdc-class.md#realizepalette)です。  
  
 Windows 構造体について詳しく**受け取る**を参照してください[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd162769)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DIBLOOK](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)



