---
title: CBitmap クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
dev_langs:
- C++
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5b931c7ad4b560ce247f78dcb126f9669bceb67
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cbitmap-class"></a>CBitmap クラス
Windows のグラフィック デバイス インターフェイス (GDI: Graphics Device Interface) のビットマップをカプセル化したもので、ビットマップを操作するためのメンバー関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|`CBitmap` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|デバイスに依存するメモリのビットマップを指定した幅、高さ、およびビット パターンでオブジェクトを初期化します。|  
|[Cbitmap::createbitmapindirect](#createbitmapindirect)|指定された幅、高さ、および (指定されている) 場合、ビット パターンを持つビットマップでオブジェクトを初期化します、**ビットマップ**構造体。|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|指定したデバイスと互換性があるように、ビットマップでオブジェクトを初期化します。|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|指定したデバイスと互換性があるビットマップを破棄できるオブジェクトを初期化します。|  
|[CBitmap::FromHandle](#fromhandle)|ポインターを返します、`CBitmap`オブジェクト ハンドルを指定して、Windows にとき`HBITMAP`ビットマップ。|  
|[CBitmap::GetBitmap](#getbitmap)|入力、**ビットマップ**ビットマップについての情報を含む構造体。|  
|[列](#getbitmapbits)|指定したビットマップのビットを指定されたバッファーにコピーします。|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|ビットマップの高さと幅を返します。 高さと幅と見なされます以前に設定されて、[呼び出す](#setbitmapdimension)メンバー関数。|  
|[CBitmap::LoadBitmap](#loadbitmap)|アプリケーションの実行可能ファイルの名前付きのビットマップ リソースを読み込むと、オブジェクトへのビットマップのアタッチによって、オブジェクトを初期化します。|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|ビットマップを読み込んで、現在のシステム カラーを色にマップします。|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|定義済みの Windows ビットマップを読み込み、ビットマップをオブジェクトにアタッチして、オブジェクトを初期化します。|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|ビットマップのビットを指定されたビット値に設定します。|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|0.1 ミリメートル単位でのビットマップの幅と高さを割り当てます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmap::operator HBITMAP](#operator_hbitmap)|接続されている Windows ハンドルを返します、`CBitmap`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 使用する、`CBitmap`オブジェクト、オブジェクトを構築、初期化のメンバー関数のいずれかにビットマップのハンドルをアタッチ、および関数を呼び出して、オブジェクトのメンバーです。  
  
 などのグラフィック オブジェクトを使用する方法についての`CBitmap`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cbitmap"></a>  CBitmap::CBitmap  
 `CBitmap` オブジェクトを構築します。  
  
```  
CBitmap();
```  
  
### <a name="remarks"></a>コメント  
 結果のオブジェクトは、メンバーの初期化関数のいずれかで初期化する必要があります。  
  
##  <a name="createbitmap"></a>  CBitmap::CreateBitmap  
 指定した幅、高さ、ビット パターンに設定されている、デバイス依存のメモリ ビットマップを初期化します。  
  
```  
BOOL CreateBitmap(
    int nWidth,  
    int nHeight,  
    UINT nPlanes,  
    UINT nBitcount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 ビットマップの幅 (ピクセル単位) を指定します。  
  
 `nHeight`  
 ビットマップの高さ (ピクセル単位) を指定します。  
  
 `nPlanes`  
 ビットマップ内でのカラー プレーンの数を指定します。  
  
 `nBitcount`  
 表示ピクセルごとのカラー ビット数を指定します。  
  
 `lpBits`  
 初期のビットマップのビット値を含むバイト配列を指します。 **NULL**の場合、新しいビットマップは初期化されないままになります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 カラー ビットマップの場合、 `nPlanes` パラメーターまたは `nBitcount` パラメーターを 1 に設定する必要があります。 両方のパラメーターを 1 に設定すると、 `CreateBitmap` によってモノクロのビットマップが作成されます。  
  
 使用して現在の「メモリ デバイス コンテキスト」ビットマップとして選択するビットマップは、ディスプレイ デバイスの直接選択することはできません、 [cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject) を使用して任意の互換性のあるデバイスコンテキストにコピーおよび[Cdc::bitblt](../../mfc/reference/cdc-class.md#bitblt)関数。  
  
 `CBitmap` 関数によって作成された `CreateBitmap` オブジェクトでの作業終了後、デバイス コンテキスト外のビットマップを最初に選択し、次に `CBitmap` オブジェクトを削除します。  
  
 詳しくは、 **BITMAP** 構造体の **bmBits** フィールドに関する記述をご覧ください。 [ビットマップ](../../mfc/reference/bitmap-structure.md)構造は」の説明、 [cbitmap::createbitmapindirect](#createbitmapindirect)メンバー関数。  
  
##  <a name="createbitmapindirect"></a>  Cbitmap::createbitmapindirect  
 幅、高さ、およびが指す構造体で指定されたビット パターン (1 つは、指定した場合) のあるビットマップを初期化します`lpBitmap`です。  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBitmap`  
 指す、[ビットマップ](../../mfc/reference/bitmap-structure.md)ビットマップについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用してメモリ デバイス コンテキストの現在のビットマップとして選択するビットマップは、ディスプレイ デバイスの直接選択することはできません、 [cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject) を使用して任意の互換性のあるデバイスコンテキストにコピーおよび[Cdc::bitblt](../../mfc/reference/cdc-class.md#bitblt)または[CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt)関数。 (、 [Cdc::patblt](../../mfc/reference/cdc-class.md#patblt)関数は、現在のブラシのビットマップをディスプレイ デバイス コンテキストに直接コピーできます)。  
  
 場合、**ビットマップ**構造体を指す、`lpBitmap`パラメーター値が入力されたを使用して、`GetObject`関数の場合、ビットマップのビットが指定されていないと、ビットマップは初期化されていません。 ビットマップを初期化するために、アプリケーション、関数など、使用できる[cdc::bitblt](../../mfc/reference/cdc-class.md#bitblt)または[SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973)の最初のパラメーターで識別されるビットマップのビットをコピーする`CGdiObject::GetObject`によって作成されたビットマップ`CreateBitmapIndirect`.  
  
 使用が終了したら、`CBitmap`オブジェクトを作成した`CreateBitmapIndirect`関数の最初にデバイス コンテキスト外のビットマップを選択し、削除、`CBitmap`オブジェクト。  
  
##  <a name="createcompatiblebitmap"></a>  CBitmap::CreateCompatibleBitmap  
 指定されたデバイスと互換性があるビットマップを初期化します`pDC`です。  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストを指定します。  
  
 `nWidth`  
 ビットマップの幅 (ピクセル単位) を指定します。  
  
 `nHeight`  
 ビットマップの高さ (ピクセル単位) を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、同じ数のカラー プレーンまたは指定したデバイス コンテキストと同じビット/ピクセル形式を持ちます。 指定された 1 つと互換性がある任意のメモリ デバイスの現在のビットマップとして選択できる`pDC`です。  
  
 場合`pDC`メモリ デバイス コンテキストでは、返されるビットマップは、そのデバイス コンテキストで現在選択されているビットマップと同じ形式を持ちます。 「メモリ デバイス コンテキスト」は、表示画面を表すメモリのブロックです。 これは、互換性のあるデバイスの実際の表示画面にコピーする前にメモリ内のイメージを準備するのに使用できます。  
  
 メモリ デバイス コンテキストが作成されると、GDI は自動的にそのストックのモノクロ ビットマップを選択します。  
  
 ビットマップの形式がによって返される色メモリ デバイス コンテキストは、カラーかモノクロ ビットマップの選択には、ので、`CreateCompatibleBitmap`関数は常に同じですただし、メモリ デバイス コンテキストの互換性のあるビットマップの形式は常に、。デバイスの形式です。  
  
 使用が終了したら、`CBitmap`で作成されたオブジェクト、`CreateCompatibleBitmap`関数の最初にデバイス コンテキスト外のビットマップを選択し、削除、`CBitmap`オブジェクト。  
  
##  <a name="creatediscardablebitmap"></a>  CBitmap::CreateDiscardableBitmap  
 によって識別されるデバイス コンテキストと互換性がある破棄できるビットマップを初期化します`pDC`です。  
  
```  
BOOL CreateDiscardableBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストを指定します。  
  
 `nWidth`  
 (Bits) で、ビットマップの幅を指定します。  
  
 `nHeight`  
 (Bits) で、ビットマップの高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、同じ数のカラー プレーンまたは指定したデバイス コンテキストと同じビット/ピクセル形式を持ちます。 アプリケーションは、によって指定されたものと互換性があるメモリ デバイスの現在のビットマップとしてこのビットマップを選択できる`pDC`です。  
  
 Windows では、アプリケーションが選択されていない、ディスプレイ コンテキストに場合にのみ、この関数によって作成されたビットマップを破棄できます。 Windows は、選択されていない、後でアプリケーションが、それを選択しようとした場合にビットマップを破棄する場合、 [cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject)関数が返す**NULL**です。  
  
 使用が終了したら、`CBitmap`で作成されたオブジェクト、`CreateDiscardableBitmap`関数の最初にデバイス コンテキスト外のビットマップを選択し、削除、`CBitmap`オブジェクト。  
  
##  <a name="fromhandle"></a>  CBitmap::FromHandle  
 ポインターを返します、 `CBitmap` Windows GDI ビットマップへのハンドルが指定されるとします。  
  
```  
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `hBitmap`  
 Windows GDI ビットマップを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CBitmap`それ以外の成功した場合は、オブジェクト**NULL**です。  
  
### <a name="remarks"></a>コメント  
 場合、`CBitmap`オブジェクトが、一時的なハンドルに既にアタッチされていない`CBitmap`オブジェクトが作成され、接続されています。 この一時`CBitmap`オブジェクトが有効では、次回アプリケーションがある移動するまでのアイドル時間イベント ループで、すべて一時的なグラフィックを時間でオブジェクトが削除専用です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に、一時オブジェクトが有効でのみことです。  
  
##  <a name="getbitmap"></a>  CBitmap::GetBitmap  
 に対して割り当てられているビットマップ イメージのプロパティを取得します。  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitMap`  
 ポインター、 [BITMAP 構造体](../../mfc/reference/bitmap-structure.md)イメージのプロパティを受信する構造体。 このパラメーターは `NULL` にすることはできません。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getbitmapbits"></a>  列  
 指定されたバッファーに割り当てられているビットマップのビット パターンをコピーします。  
  
```  
DWORD GetBitmapBits(
    DWORD dwCount,  
    LPVOID lpBits) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCount`  
 バッファーにコピーするバイト数。  
  
 `lpBits`  
 ビットマップを受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、バッファーにコピーされたバイト数それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して[CBitmap::GetBitmap](#getbitmap)が必要なバッファー サイズを決定します。  
  
##  <a name="getbitmapdimension"></a>  CBitmap::GetBitmapDimension  
 ビットマップの高さと幅を返します。  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップの高さと幅は、0.1 ミリメートル単位で測定されます。 高さは、 **cy**のメンバー、`CSize`オブジェクト、および幅では、 **cx**メンバー。 ビットマップの幅と高さが設定されていないを使用して場合`SetBitmapDimension`、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 高さと幅を使用して、以前に設定されていると見なされます、[呼び出す](#setbitmapdimension)メンバー関数。  
  
##  <a name="loadbitmap"></a>  CBitmap::LoadBitmap  
 によって指定されたビットマップ リソースを読み込みます`lpszResourceName`の ID 番号で識別されるまたは`nIDResource`アプリケーションの実行可能ファイルからです。  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 ビットマップ リソースの名前を表す null で終わる文字列へのポインター。  
  
 `nIDResource`  
 ビットマップ リソースのリソースの ID 番号を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 読み込まれたビットマップが接続されている、`CBitmap`オブジェクト。  
  
 によって識別されるビットマップ場合`lpszResourceName`存在しませんまたはビットマップの読み込みが不足しているメモリがある場合、0 を返します。  
  
 使用することができます、 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)によって読み込まれるビットマップを削除する関数、`LoadBitmap`関数、または`CBitmap`デストラクターのオブジェクトが削除されます。  
  
> [!CAUTION]
>  オブジェクトを削除する前に、デバイス コンテキストに選択されていないことを確認してください。  
  
 次のビットマップは、Windows のバージョン 3.1 以降に追加されました。  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 これらのビットマップは 3.0 と以前のバージョンの Windows デバイス ドライバーで見つかりませんでした。 ビットマップと表示形式の完全な一覧は、Windows SDK を参照してください。  
  
##  <a name="loadmappedbitmap"></a>  CBitmap::LoadMappedBitmap  
 ビットマップを読み込んで、現在のシステム カラーを色にマップするには、このメンバー関数を呼び出します。  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDBitmap`  
 ビットマップ リソースの ID。  
  
 `nFlags`  
 ビットマップのフラグ。 0 または**CMB_MASKED**です。  
  
 `lpColorMap`  
 ポインター、**カラー マップ**ビットマップをマップするために必要な色の情報を格納する構造体。 このパラメーターが場合**NULL**関数は既定のカラー マップを使用します。  
  
 *nMapSize*  
 マップの色の数を指す`lpColorMap`です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、`LoadMappedBitmap`ボタン グリフでよく使用される色をマップします。  
  
 マップされたビットマップを作成する方法の詳細については、Windows の関数を参照してください。 [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562)と[カラー マップ](http://msdn.microsoft.com/library/windows/desktop/bb760448)Windows SDK 内の構造。  
  
##  <a name="loadoembitmap"></a>  CBitmap::LoadOEMBitmap  
 Windows で使用される定義済みのビットマップを読み込みます。  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDBitmap`  
 定義済みの Windows ビットマップの ID 番号。 使用可能な値は、WINDOWS から次に示します。H:  
  
|||  
|-|-|  
|**OBM_BTNCORNERS**|**OBM_OLD_RESTORE**|  
|**OBM_BTSIZE**|**OBM_OLD_RGARROW**|  
|**OBM_CHECK**|**OBM_OLD_UPARROW**|  
|**OBM_CHECKBOXES**|**OBM_OLD_ZOOM**|  
|**OBM_CLOSE**|**OBM_REDUCE**|  
|**OBM_COMBO**|**OBM_REDUCED**|  
|**OBM_DNARROW**|**OBM_RESTORE**|  
|**OBM_DNARROWD**|**OBM_RESTORED**|  
|**OBM_DNARROWI**|**OBM_RGARROW**|  
|**OBM_LFARROW**|**OBM_RGARROWD**|  
|**OBM_LFARROWD**|**OBM_RGARROWI**|  
|**OBM_LFARROWI**|**OBM_SIZE**|  
|**OBM_MNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_CLOSE**|**OBM_UPARROWD**|  
|**OBM_OLD_DNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_LFARROW**|**OBM_ZOOM**|  
|**OBM_OLD_REDUCE**|**OBM_ZOOMD**|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットマップの名前で始まる**OBM_OLD** 3.0 より前のバージョンの Windows で使用されるビットマップを表します。  
  
 なお、定数**OEMRESOURCE** WINDOWS をインクルードする前に定義する必要があります。H のいずれかを使用するために、 **OBM_** 定数。  
  
##  <a name="operator_hbitmap"></a>  CBitmap::operator HBITMAP  
 この演算子のアタッチされた Windows GDI ハンドルの取得を使用して、`CBitmap`オブジェクト。  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CBitmap`オブジェクト。 それ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 この演算子はキャスト演算子の`HBITMAP`オブジェクト。  
  
 グラフィック オブジェクトの使用に関する詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)Windows SDK に含まれています。  
  
##  <a name="setbitmapbits"></a>  CBitmap::SetBitmapBits  
 によって指定されたビット値にビットマップのビットを設定`lpBits`です。  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCount`  
 によって示されるバイト数を指定`lpBits`です。  
  
 `lpBits`  
 指す、**バイト**配列にコピーするピクセルの値を含む、`CBitmap`オブジェクト。 ビットマップをそのイメージは正しく表示できるためには、値を CBitmap インスタンスの作成時に指定された高さ、幅、および色深度値に準拠するようにフォーマットされている必要があります。 詳細については、次を参照してください。 [CBitmap::CreateBitmap](#createbitmap)です。  
  
### <a name="return-value"></a>戻り値  
 ビットマップのビットを設定で使用されるバイト数関数が失敗した場合は 0 を返します。  
  
##  <a name="setbitmapdimension"></a>  CBitmap::SetBitmapDimension  
 0.1 ミリメートル単位でのビットマップの幅と高さを割り当てます。  
  
```  
CSize SetBitmapDimension(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 (0.1 ミリメートル単位) で、ビットマップの幅を指定します。  
  
 `nHeight`  
 (0.1 ミリメートル単位) で、ビットマップの高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 以前のビットマップの寸法。 高さは、 **cy**のメンバー変数、`CSize`オブジェクト、および幅では、 **cx**メンバー変数。  
  
### <a name="remarks"></a>コメント  
 GDI が以外に、それらが戻りますアプリケーションを呼び出すときにこれらの値を使用していない、 [GetBitmapDimension](#getbitmapdimension)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)

