---
title: CMFCFontInfo クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27858b6dad2744965e85bcd8287ba62cbf5b60c0
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038602"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo クラス
`CMFCFontInfo`クラスは、名前とフォントの他の属性について説明します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCFontInfo`|`CMFCFontInfo` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|連結した名前、フォントとその文字セット (スクリプト) を取得します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|フォントに関連付けられている文字セット (スクリプト) を指定する値。|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|ピッチとファミリのフォントを指定する値。|  
|[CMFCFontInfo::m_nType](#m_ntype)|フォントの種類を指定する値。|  
|[CMFCFontInfo::m_strName](#m_strname)|フォントの名前たとえば、 **Arial**です。|  
|[CMFCFontInfo::m_strScript](#m_strscript)|フォントに関連付けられている文字セット (スクリプト) の名前。|  
  
## <a name="remarks"></a>Remarks  
 アタッチすることができます、`CMFCFontInfo`オブジェクトの項目を[CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)クラスです。 呼び出す、 [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc)へのポインターを取得する方法を`CMFCFontInfo`オブジェクト。  
  
## <a name="example"></a>例  
 次の例でのさまざまなメンバーを使用する方法、`CMFCFontInfo`クラスです。 例では、取得する方法を示します、`CMFCFontInfo`オブジェクトから、 `CMFCRibbonFontComboBox`、およびそのローカル変数にアクセスする方法です。 この例の一部である、 [MSOffice 2007 デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfcfontinfo"></a>  CMFCFontInfo::CMFCFontInfo  
 `CMFCFontInfo` オブジェクトを構築します。  
  
```  
CMFCFontInfo(
    LPCTSTR lpszName,  
    LPCTSTR lpszScript,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily,  
    int nType);  
  
CMFCFontInfo(const CMFCFontInfo& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszName*  
 フォントの名前です。 詳細については、次を参照してください。、`lfFaceName`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
 [in]*lpszScript*  
 フォントのスクリプト (文字セット) の名前。  
  
 [in]*nCharSet*  
 フォントの文字セット (スクリプト) を指定する値。 詳細については、次を参照してください。、`lfCharSet`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
 [in]*nPitchAndFamily*  
 ピッチとファミリのフォントを指定する値。 詳細については、次を参照してください。、`lfPitchAndFamily`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
 [in]*タイプ*  
 フォントの種類を指定する値。 このパラメーターは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE のビットごとの組み合わせ (OR) を指定できます。  
  
 [in]*src*  
 既存の`CMFCFontInfo`のメンバーが構築するために使用されるオブジェクト`CMFCFontInfo`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
 このドキュメントでは、用語*文字セット*と*スクリプト*同義です。 A*スクリプト*文字と 1 つまたは複数の言語でこれらの文字を書き込むための規則のコレクションは、これは、書記体系でとも呼ばれます。 文字のコレクションには、アルファベットとそのスクリプトで使用される区切り記号が含まれています。 たとえば、これは、米国の読み上げし、のアルファベットには、a ~ Z の文字が含まれています。 英語のラテン文字は使用されます。`lfCharSet`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体は、文字セットを指定します。 たとえば、値`ANSI_CHARSET`を指定します、[!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)]文字セットは、ラテン文字の文字が含まれています。  
  
##  <a name="getfullname"></a>  CMFCFontInfo::GetFullName  
 連結した名前、フォントとその文字セット (スクリプト) を取得します。  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スクリプトとフォントの名前を表す文字列。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用すると、フォントの完全な名前を取得できます。 たとえば、フォント名がある場合は`Arial`、およびフォント スクリプトが`Cyrillic`、このメソッドは、Arial (キリル文字) を返します。  
  
##  <a name="m_ncharset"></a>  CMFCFontInfo::m_nCharSet  
 フォントに関連付けられている文字セット (スクリプト) を指定する値。  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、 *nCharSet*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
##  <a name="m_npitchandfamily"></a>  CMFCFontInfo::m_nPitchAndFamily  
 (ポイントのサイズ) のピッチとファミリ (たとえば、serif、sans serif と固定幅) フォントを指定する値。  
  
```  
const BYTE m_nPitchAndFamily;  
```  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、 *nPitchAndFamily*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
##  <a name="m_ntype"></a>  CMFCFontInfo::m_nType  
 フォントの種類を指定する値。  
  
```  
const int m_nType;  
```  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、*タイプ*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
##  <a name="m_strname"></a>  CMFCFontInfo::m_strName  
 フォントの名前。 たとえば、 **Arial**です。  
  
```  
const CString m_strName;  
```  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、 *lpszName*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
##  <a name="m_strscript"></a>  CMFCFontInfo::m_strScript  
 フォントに関連付けられている文字セット (スクリプト) の名前。  
  
```  
const CString m_strScript;  
```  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、 *lpszScript*のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox クラス](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
