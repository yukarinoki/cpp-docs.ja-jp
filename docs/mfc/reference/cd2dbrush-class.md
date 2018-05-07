---
title: CD2DBrush クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 324e6411673a509bdf75954634ff9c6dffc5ce1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dbrush-class"></a>CD2DBrush クラス
ID2D1Brush のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|CD2DBrush オブジェクトを構築します。|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|デストラクターです。 D2D ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|既存のリソースのインターフェイス オブジェクトへの接続|  
|[CD2DBrush::Destroy](#destroy)|CD2DBrush オブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DBrush::Detach](#detach)|オブジェクトからリソースのインターフェイスの関連付けを解除します。|  
|[CD2DBrush::Get](#get)|返します ID2D1Brush インターフェイス|  
|[CD2DBrush::GetOpacity](#getopacity)|このブラシの不透明度を取得します。|  
|[CD2DBrush::GetTransform](#gettransform)|レンダー ターゲットの現在の変換を取得します。|  
|[CD2DBrush::IsValid](#isvalid)|リソースの有効性をチェック (オーバーライド[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
|[CD2DBrush::SetOpacity](#setopacity)|このブラシの不透明度を設定します。|  
|[CD2DBrush::SetTransform](#settransform)|既存の変換を置き換える、レンダー ターゲットを指定した変換を適用します。 変換後のスペースにすべての後続の描画操作が発生します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|返します ID2D1Brush インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|ID2D1Brush オブジェクトへのポインターを格納します。|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|ブラシのプロパティです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>  CD2DBrush:: ~ CD2DBrush  
 デストラクターです。 D2D ブラシ オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>  CD2DBrush::Attach  
 既存のリソースのインターフェイス オブジェクトへの接続  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL をすることはできません。  
  
##  <a name="cd2dbrush"></a>  CD2DBrush::CD2DBrush  
 CD2DBrush オブジェクトを構築します。  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `pBrushProperties`  
 不透明度およびブラシの変換へのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="destroy"></a>  CD2DBrush::Destroy  
 CD2DBrush オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DBrush::Detach  
 オブジェクトからリソースのインターフェイスの関連付けを解除します。  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソースのインターフェイスへのポインター。  
  
##  <a name="get"></a>  CD2DBrush::Get  
 返します ID2D1Brush インターフェイス  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1Brush インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="getopacity"></a>  CD2DBrush::GetOpacity  
 このブラシの不透明度を取得します。  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 ~ ブラシの不透明度を示す 1 の値。 この値は、直線的にブラシで埋められたすべてのピクセルのアルファ値をスケーリングする定数乗数です。 乗算は前に、不透明度の値は 0 ~ 1 の範囲内で固定されます。  
  
##  <a name="gettransform"></a>  CD2DBrush::GetTransform  
 レンダー ターゲットの現在の変換を取得します。  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `transform`  
 このエラーが返されるときに、レンダー ターゲットの現在の変換が含まれています。 このパラメーターは初期化せずに渡されます  
  
##  <a name="isvalid"></a>  CD2DBrush::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_pbrush"></a>  CD2DBrush::m_pBrush  
 ID2D1Brush オブジェクトへのポインターを格納します。  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>  CD2DBrush::m_pBrushProperties  
 ブラシのプロパティです。  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>  CD2DBrush::operator ID2D1Brush *  
 返します ID2D1Brush インターフェイス  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1Brush インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="setopacity"></a>  CD2DBrush::SetOpacity  
 このブラシの不透明度を設定します。  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>パラメーター  
 `opacity`  
 0 ~ ブラシの不透明度を示す 1 の値。 この値は、直線的にブラシで埋められたすべてのピクセルのアルファ値をスケーリングする定数乗数です。 乗算は前に、不透明度の値は 0 ~ 1 の範囲内で固定されます。  
  
##  <a name="settransform"></a>  CD2DBrush::SetTransform  
 既存の変換を置き換える、レンダー ターゲットを指定した変換を適用します。 変換後のスペースにすべての後続の描画操作が発生します。  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>パラメーター  
 `transform`  
 レンダー ターゲットに適用する変換  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
