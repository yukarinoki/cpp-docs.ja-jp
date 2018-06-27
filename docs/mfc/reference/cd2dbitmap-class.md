---
title: CD2DBitmap クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e37a8329e0afaa26b114d0ae0da53f0ec552e09e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954750"
---
# <a name="cd2dbitmap-class"></a>CD2DBitmap クラス
ID2D1Bitmap のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|オーバーロードされます。 HBITMAP から CD2DBitmap オブジェクトを構築します。|  
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|デストラクターです。 D2D ビットマップ オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|オーバーロードされます。 CD2DBitmap オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::Attach](#attach)|既存のリソースのインターフェイス オブジェクトへの接続|  
|[CD2DBitmap::CopyFromBitmap](#copyfrombitmap)|指定した領域を指定したビットマップから現在のビットマップにコピーします。|  
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|指定した領域をメモリから現在のビットマップにコピーします。|  
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|現在のビットマップにコピーから、指定した指定した領域のレンダリング ターゲット|  
|[CD2DBitmap::Create](#create)|CD2DBitmap を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DBitmap::Destroy](#destroy)|CD2DBitmap オブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DBitmap::Detach](#detach)|オブジェクトからリソースのインターフェイスの関連付けを解除します。|  
|[CD2DBitmap::Get](#get)|返します ID2D1Bitmap インターフェイス|  
|[CD2DBitmap::GetDPI](#getdpi)|ドット/インチ (DPI) のビットマップを返す|  
|[CD2DBitmap::GetPixelFormat](#getpixelformat)|ビットマップのピクセル形式とアルファ モードを取得します。|  
|[CD2DBitmap::GetPixelSize](#getpixelsize)|ビットマップのサイズをデバイスに依存しない単位 (ピクセル単位) を返します|  
|[CD2DBitmap::GetSize](#getsize)|ビットマップのサイズをデバイスに依存しないピクセル単位 (Dip) を返します|  
|[CD2DBitmap::IsValid](#isvalid)|リソースの有効性をチェック (オーバーライド[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::CommonInit](#commoninit)|オブジェクトを初期化します|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|返します ID2D1Bitmap インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CD2DBitmap::m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|TRUE の場合、m_hBmpSrc を破棄する必要があります。それ以外の場合は FALSE。|  
|[CD2DBitmap::m_hBmpSrc](#m_hbmpsrc)|ソース ビットマップのハンドルです。|  
|[CD2DBitmap::m_lpszType](#m_lpsztype)|リソースの種類。|  
|[CD2DBitmap::m_pBitmap](#m_pbitmap)|ID2D1Bitmap オブジェクトへのポインターを格納します。|  
|[CD2DBitmap::m_sizeDest](#m_sizedest)|コピー先のサイズをビットマップします。|  
|[CD2DBitmap::m_strPath](#m_strpath)|Botmap ファイルのパス。|  
|[CD2DBitmap::m_uiResID](#m_uiresid)|ビットマップのリソース id です。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBitmap`
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbitmap"></a>  CD2DBitmap:: ~ CD2DBitmap  
 デストラクターです。 D2D ビットマップ オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DBitmap();
```  
  
##  <a name="attach"></a>  CD2DBitmap::Attach  
 既存のリソースのインターフェイス オブジェクトへの接続  
  
```  
void Attach(ID2D1Bitmap* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 *pResource*  
 既存のリソースのインターフェイスです。 NULL をすることはできません。  
  
##  <a name="cd2dbitmap"></a>  CD2DBitmap::CD2DBitmap  
 リソースから CD2DBitmap オブジェクトを構築します。  
  
```  
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszPath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    HBITMAP hbmpSrc,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentTarget*  
 レンダー ターゲットへのポインター。  
  
 *uiResID*  
 リソースのリソース ID 番号。  
  
 *lpszType*  
 リソースの種類を表す null で終わる文字列へのポインター。  
  
 *sizeDest*  
 ビットマップの送信先のサイズ。  
  
 *bAutoDestroy*  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
 *lpszPath*  
 ファイルの名前を表す null で終わる文字列へのポインター。  
  
 *hbmpSrc*  
 ビットマップへのハンドルします。  
  
##  <a name="commoninit"></a>  CD2DBitmap::CommonInit  
 オブジェクトを初期化します  
  
```  
void CommonInit();
```  
  
##  <a name="copyfrombitmap"></a>  CD2DBitmap::CopyFromBitmap  
 指定した領域を指定したビットマップから現在のビットマップにコピーします。  
  
```  
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pBitmap*  
 コピー元ビットマップ  
  
 *destPoint*  
 現在のビットマップ srcRect でする領域が指定された領域の左上隅のコピーします。  
  
 *srcRect*  
 コピーするビットマップの領域  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="copyfrommemory"></a>  CD2DBitmap::CopyFromMemory  
 指定した領域をメモリから現在のビットマップにコピーします。  
  
```  
HRESULT CopyFromMemory(
    const void* srcData,  
    UINT32 pitch,  
    const CD2DRectU* destRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *srcData*  
 コピーするデータ  
  
 *声の高さ*  
 ストライド、または srcData に格納されている元のビットマップの声の高さ。 Stride とは、スキャン ライン (メモリ内のピクセルの 1 つの行) のバイト数です。 Stride は次の数式に基づいて計算されます: ピクセル幅 * ピクセル + メモリ スペースあたりのバイト数  
  
 *destRect*  
 現在のビットマップ srcRect でする領域が指定された領域の左上隅のコピーします。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="copyfromrendertarget"></a>  CD2DBitmap::CopyFromRenderTarget  
 現在のビットマップにコピーから、指定した指定した領域のレンダリング ターゲット  
  
```  
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRenderTarget*  
 レンダー ターゲットをコピーする領域を含む  
  
 *destPoint*  
 現在のビットマップ srcRect でする領域が指定された領域の左上隅のコピーします。  
  
 *srcRect*  
 コピーするレンダリング ターゲットの領域  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="create"></a>  CD2DBitmap::Create  
 CD2DBitmap を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRenderTarget*  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>  CD2DBitmap::Destroy  
 CD2DBitmap オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DBitmap::Detach  
 オブジェクトからリソースのインターフェイスの関連付けを解除します。  
  
```  
ID2D1Bitmap* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソースのインターフェイスへのポインター。  
  
##  <a name="get"></a>  CD2DBitmap::Get  
 返します ID2D1Bitmap インターフェイス  
  
```  
ID2D1Bitmap* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1Bitmap インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="getdpi"></a>  CD2DBitmap::GetDPI  
 ドット/インチ (DPI) のビットマップを返す  
  
```  
CD2DSizeF GetDPI() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップの水平方向および垂直 DPI。  
  
##  <a name="getpixelformat"></a>  CD2DBitmap::GetPixelFormat  
 ビットマップのピクセル形式とアルファ モードを取得します。  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップのピクセル形式とアルファ モードです。  
  
##  <a name="getpixelsize"></a>  CD2DBitmap::GetPixelSize  
 ビットマップのサイズをデバイスに依存しない単位 (ピクセル単位) を返します  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップのピクセル単位のサイズ.  
  
##  <a name="getsize"></a>  CD2DBitmap::GetSize  
 ビットマップのサイズをデバイスに依存しないピクセル単位 (Dip) を返します  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Dip は、ビットマップのサイズ。  
  
##  <a name="isvalid"></a>  CD2DBitmap::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_bautodestroyhbmp"></a>  CD2DBitmap::m_bAutoDestroyHBMP  
 TRUE の場合、m_hBmpSrc を破棄する必要があります。それ以外の場合は FALSE。  
  
```  
BOOL m_bAutoDestroyHBMP;  
```  
  
##  <a name="m_hbmpsrc"></a>  CD2DBitmap::m_hBmpSrc  
 ソース ビットマップのハンドルです。  
  
```  
HBITMAP m_hBmpSrc;  
```  
  
##  <a name="m_lpsztype"></a>  CD2DBitmap::m_lpszType  
 リソースの種類。  
  
```  
LPCTSTR m_lpszType;  
```  
  
##  <a name="m_pbitmap"></a>  CD2DBitmap::m_pBitmap  
 ID2D1Bitmap オブジェクトへのポインターを格納します。  
  
```  
ID2D1Bitmap* m_pBitmap;  
```  
  
##  <a name="m_sizedest"></a>  CD2DBitmap::m_sizeDest  
 コピー先のサイズをビットマップします。  
  
```  
CD2DSizeU m_sizeDest;  
```  
  
##  <a name="m_strpath"></a>  CD2DBitmap::m_strPath  
 Botmap ファイルのパス。  
  
```  
CString m_strPath;  
```  
  
##  <a name="m_uiresid"></a>  CD2DBitmap::m_uiResID  
 ビットマップのリソース id です。  
  
```  
UINT m_uiResID;  
```  
  
##  <a name="operator_id2d1bitmap_star"></a>  CD2DBitmap::operator ID2D1Bitmap *  
 返します ID2D1Bitmap インターフェイス  
  
```  
operator ID2D1Bitmap*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1Bitmap インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
