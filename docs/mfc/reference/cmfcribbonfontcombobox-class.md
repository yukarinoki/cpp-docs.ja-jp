---
title: CMFCRibbonFontComboBox クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86a46614cdb61e39af1016e496b12518b87f59ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370508"
---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox クラス
フォントの一覧を含むコンボ ボックスを実装します。 このコンボ ボックスをリボン パネルに配置できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|デストラクターです。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|`CMFCRibbonFontComboBox` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|リボンのフォント コンボ ボックスに、指定されたフォントの種類、文字セット、ピッチ、ファミリのフォントを設定します。|  
|`CMFCRibbonFontComboBox::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|指定された文字セットを返します。|  
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||  
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|コンボ ボックスに表示するフォントの種類を返します。 有効なオプションは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE、またはそのビットごとの任意の組み合わせです。|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|コンボ ボックスに表示されるフォントのピッチとファミリを返します。|  
|`CMFCRibbonFontComboBox::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|リボンのフォント コンボ ボックスに、以前に指定されたフォントの種類、文字セット、ピッチ、ファミリのフォントを設定します。|  
|[CMFCRibbonFontComboBox::SetFont](#setfont)|コンボ ボックスで、指定されたフォントを選択します。|  
  
## <a name="remarks"></a>コメント  
 作成した後、`CMFCRibbonFontComboBox`オブジェクトを呼び出してリボン パネルに追加[cmfcribbonpanel::add](../../mfc/reference/cmfcribbonpanel-class.md#add)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonComboBox.h  
  
##  <a name="buildfonts"></a>  CMFCRibbonFontComboBox::BuildFonts  
 フォントでリボンのコンボ ボックスに表示します。  
  
```  
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFontType`  
 追加するフォントのフォントの種類を指定します。  
  
 [入力] `nCharSet`  
 追加するフォントの文字セットを指定します。  
  
 [入力] `nPitchAndFamily`  
 ピッチとファミリを追加するフォントを指定します。  
  
##  <a name="cmfcribbonfontcombobox"></a>  CMFCRibbonFontComboBox::CMFCRibbonFontComboBox  
 構築して初期化、 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)オブジェクト。  
  
```  
CMFCRibbonFontComboBox(
    UINT nID,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH,  
    int nWidth = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 ユーザーが、コンボ ボックスから項目を選択したときに実行されるコマンドのコマンド ID。  
  
 [入力] `nFontType`  
 コンボ ボックスに表示するフォントの種類を指定します。 有効なオプションは**DEVICE_FONTTYPE**、 **RASTER_FONTTYPE**、および**TRUETYPE_FONTTYPE**、または、ビットごとの組み合わせ。  
  
 [入力] `nCharSet`  
 指定された文字セットに属するものにコンボ ボックス内のフォントをフィルター処理には.  
  
 [入力] `nPitchAndFamily`  
 ピッチとファミリのコンボ ボックスに表示されるフォントを指定します。  
  
 [入力] `nWidth`  
 コンボ ボックスのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
 可能な限りの詳細については`nFontType`パラメーター値を参照してください[EnumFontFamProc](http://msdn.microsoft.com/library/windows/desktop/dd162621) Windows SDK のドキュメントです。  
  
 割り当てることができる有効な文字セットの詳細については`nCharSet`とに割り当てることができる有効な値`nPitchAndFamily`を参照してください[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Windows SDK のドキュメントです。  
  
##  <a name="getfontdesc"></a>  CMFCRibbonFontComboBox::GetFontDesc  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="rebuildfonts"></a>  CMFCRibbonFontComboBox::RebuildFonts  
 以前に指定したフォントの種類、文字セット、ピッチとファミリのフォントでリボンのコンボ ボックスに表示します。  
  
```  
void RebuildFonts();
```  
  
### <a name="remarks"></a>コメント  
 フォントの種類、文字セットを指定して、リボンのフォント コンボ ボックスで、フォントのピッチとファミリのボックスに、[コンス トラクター](#cmfcribbonfontcombobox)または呼び出すことによって、このクラスに対して[CMFCRibbonFontComboBox::BuildFonts](#buildfonts).  
  
##  <a name="setfont"></a>  CMFCRibbonFontComboBox::SetFont  
 コンボ ボックスで、指定されたフォントを選択します。  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BOOL bExact = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 選択するフォントの名前を指定します。  
  
 `nCharSet`  
 選択したフォントの文字セットを指定します。  
  
 `bExact`  
 `TRUE` 文字セットは、フォントを選択するときと一致する必要がありますを指定するには`FALSE`にフォントを選択するときに、文字セットを無視できることを指定します。  
  
### <a name="return-value"></a>戻り値  
 指定したフォントが見つかり、選択されている場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcharset"></a>  CMFCRibbonFontComboBox::GetCharSet  
 指定された文字セットを返します。  
  
```  
BYTE GetCharSet() const;  
```  
  
### <a name="return-value"></a>戻り値  
 文字セット (、Windows SDK のマニュアルで LOGFONT を参照してください)。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getfonttype"></a>  CMFCRibbonFontComboBox::GetFontType  
 コンボ ボックスに表示するフォントの種類を返します。 有効なオプションは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE、またはそのビットごとの任意の組み合わせです。  
  
```  
int GetFontType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フォントの種類 (Windows SDK ドキュメント EnumFontFamProc を参照してください)。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpitchandfamily"></a>  CMFCRibbonFontComboBox::GetPitchAndFamily  
 コンボ ボックスに表示されるフォントのピッチとファミリを返します。  
  
```  
BYTE GetPitchAndFamily() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピッチとファミリ (、Windows SDK のマニュアルで LOGFONT を参照してください)。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonComboBox クラス](../../mfc/reference/cmfcribboncombobox-class.md)
