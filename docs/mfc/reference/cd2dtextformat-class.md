---
title: CD2DTextFormat クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
dev_langs:
- C++
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e55689fa71ed5f0e4ebd4978a004212d5fb82b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352891"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat クラス
IDWriteTextFormat のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DTextFormat : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|CD2DTextFormat オブジェクトを構築します。|  
|[CD2DTextFormat:: ~ CD2DTextFormat](#cd2dtextformat__~cd2dtextformat)|デストラクターです。 D2D オブジェクトのテキスト書式設定が破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DTextFormat::Create](#create)|CD2DTextFormat を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DTextFormat::Destroy](#destroy)|CD2DTextFormat オブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DTextFormat::Get](#get)|返します IDWriteTextFormat インターフェイス|  
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|フォント ファミリ名のコピーを取得します。|  
|[CD2DTextFormat::GetLocaleName](#getlocalename)|ロケール名のコピーを取得します。|  
|[CD2DTextFormat::IsValid](#isvalid)|リソースの有効性をチェック (オーバーライド[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
|[CD2DTextFormat::ReCreate](#recreate)|CD2DTextFormat を再作成されます。 (上書き[CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DTextFormat::operator IDWriteTextFormat *](#operator_idwritetextformat_star)|返します IDWriteTextFormat インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|IDWriteTextFormat へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dtextformat"></a>  CD2DTextFormat:: ~ CD2DTextFormat  
 デストラクターです。 D2D オブジェクトのテキスト書式設定が破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DTextFormat();
```  
  
##  <a name="cd2dtextformat"></a>  CD2DTextFormat::CD2DTextFormat  
 CD2DTextFormat オブジェクトを構築します。  
  
```  
CD2DTextFormat(
    CRenderTarget* pParentTarget,  
    const CString& strFontFamilyName,  
    FLOAT fontSize,  
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,  
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,  
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,  
    const CString& strFontLocale = _T(""),  
    IDWriteFontCollection* pFontCollection = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `strFontFamilyName`  
 フォント ファミリの名前を含む CString オブジェクト。  
  
 `fontSize`  
 DIP (「デバイスに依存しないピクセル」) 単位でフォントの論理サイズ。 DIPequals 1/96 インチです。  
  
 `fontWeight`  
 テキスト オブジェクトのフォントの太さを示す値です。  
  
 `fontStyle`  
 テキスト オブジェクトのフォント スタイルを示す値です。  
  
 `fontStretch`  
 テキスト オブジェクトのフォントの伸縮を示す値です。  
  
 `strFontLocale`  
 ロケール名を含む CString オブジェクト。  
  
 `pFontCollection`  
 フォントのコレクション オブジェクトへのポインター。 これが NULL の場合は、システム フォントのコレクションを表します。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="create"></a>  CD2DTextFormat::Create  
 CD2DTextFormat を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>  CD2DTextFormat::Destroy  
 CD2DTextFormat オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="get"></a>  CD2DTextFormat::Get  
 返します IDWriteTextFormat インターフェイス  
  
```  
IDWriteTextFormat* Get();
```  
  
### <a name="return-value"></a>戻り値  
 IDWriteTextFormat インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="getfontfamilyname"></a>  CD2DTextFormat::GetFontFamilyName  
 フォント ファミリ名のコピーを取得します。  
  
```  
CString GetFontFamilyName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のフォント ファミリ名を格納する CString オブジェクト。  
  
##  <a name="getlocalename"></a>  CD2DTextFormat::GetLocaleName  
 ロケール名のコピーを取得します。  
  
```  
CString GetLocaleName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のロケール名を格納する CString オブジェクト。  
  
##  <a name="isvalid"></a>  CD2DTextFormat::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_ptextformat"></a>  CD2DTextFormat::m_pTextFormat  
 IDWriteTextFormat へのポインター。  
  
```  
IDWriteTextFormat* m_pTextFormat;  
```  
  
##  <a name="operator_idwritetextformat_star"></a>  CD2DTextFormat::operator IDWriteTextFormat *  
 返します IDWriteTextFormat インターフェイス  
  
```  
operator IDWriteTextFormat*();
```   
  
### <a name="return-value"></a>戻り値  
 IDWriteTextFormat インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="recreate"></a>  CD2DTextFormat::ReCreate  
 CD2DTextFormat を再作成されます。  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
