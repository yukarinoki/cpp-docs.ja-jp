---
title: CMFCImagePaintArea クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd5dd96c51c6b4ff5d3376581ddd760a2741968a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea クラス
イメージ エディター ダイアログ ボックスでイメージを変更するために使用ピクチャの領域を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|`CMFCImagePaintArea` オブジェクトを構築します。|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCImagePaintArea::GetMode](#getmode)|現在の描画モードを取得します。|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|画像領域のビットマップ イメージを設定します。|  
|[CMFCImagePaintArea::SetColor](#setcolor)|現在の描画の色を設定します。|  
|[CMFCImagePaintArea::SetMode](#setmode)|現在の描画モードを設定します。|  
  
### <a name="remarks"></a>コメント  
 このクラスは、コードから直接使用するものではありません。  
  
 フレームワークでは、このクラスを使用して、イメージ エディター ダイアログ ボックスで画像領域を表示します。 イメージ エディター] ダイアログ ボックスの詳細については、次を参照してください。 [[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)です。  
  
## <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCImagePaintArea`クラスは、現在の色を描画するには、現在の描画モードを設定し、画像領域のビットマップ イメージの設定を設定します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afximagepaintarea.h  
  
##  <a name="cmfcimagepaintarea"></a>  CMFCImagePaintArea::CMFCImagePaintArea  
 `CMFCImagePaintArea` オブジェクトを構築します。  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pParentDlg`|イメージ エディターの親である ダイアログ ボックスへのポインター。|  
  
##  <a name="getmode"></a>  CMFCImagePaintArea::GetMode  
 現在の描画モードを取得します。  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)現在の描画モードを指定する値。  
  
##  <a name="setbitmap"></a>  CMFCImagePaintArea::SetBitmap  
 画像領域のビットマップ イメージを設定します。  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pBitmap`|表示する新しいビットマップ イメージ。|  
  
### <a name="remarks"></a>コメント  
 場合`pBitmap`は`NULL`、このメソッドは、変更可能な描画領域のサイズを 0 に設定します。 それ以外の場合、指定されたビットマップ イメージのサイズを変更可能な描画領域のサイズを設定します。  
  
##  <a name="setcolor"></a>  CMFCImagePaintArea::SetColor  
 現在の描画の色を設定します。  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `color`|新しい図面色です。|  
  
### <a name="remarks"></a>コメント  
 ときに、イメージ エディター パレット バーから色を選択またはカラー ピッカー、フレームワークは、現在の描画の色を更新するには、このメソッドを呼び出します。 初期の描画の色は黒 (、 `COLORREF` 0 の値)。  
  
 イメージ エディター ダイアログ ボックスですべての描画モード以外の描画の色が使用される`IMAGE_EDIT_MODE_COLOR`です。 描画モードの詳細については、次を参照してください。 [cmfcimagepaintarea::image_edit_mode 列挙](cmfcimagepaintarea-image-edit-mode-enumeration.md)です。  
  
##  <a name="setmode"></a>  CMFCImagePaintArea::SetMode  
 現在の描画モードを設定します。  
  
```  
void SetMode(IMAGE_EDIT_MODE mode);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `mode`|[IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)現在の描画モードを指定する値。|  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)
