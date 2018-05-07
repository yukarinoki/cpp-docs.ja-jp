---
title: CMFCImageEditorDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 795e5548e93323af389c3faeaefa7dda0bf7d80c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog クラス
`CMFCImageEditorDialog`クラスは、イメージ エディター ダイアログ ボックスをサポートしています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|`CMFCImageEditorDialog` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCImageEditorDialog`クラスが含まれるダイアログ ボックスが表示されます。  
  
-   使用するイメージ内の個々 のピクセルを変更する画像領域。  
  
-   画像領域のピクセルを修正するためのツールを描画します。  
  
-   描画ツールによって使用される色を指定する色パレット。  
  
-   編集の影響を表示するプレビュー領域。  
  
 次の図は、イメージ エディター ダイアログ ボックスを示しています。  
  
 ![[CMFCImageEditorDialog] ダイアログ ボックス](../../mfc/reference/media/imageedit.png "imageedit")  
  
 使用する方法の 1 つ、`CMFCImageEditorDialog`オブジェクトを渡すことが、`CBitmap`イメージを編集することです。 イメージの編集領域が制限されたサイズと論理ピクセルのサイズは、領域に合わせて調整するために大きなイメージを作成できません。 呼び出す、`DoModal`モーダル ダイアログ ボックスを起動する方法です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afximageeditordialog.h  
  
##  <a name="cmfcimageeditordialog"></a>  CMFCImageEditorDialog::CMFCImageEditorDialog  
 `CMFCImageEditorDialog` オブジェクトを構築します。  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitmap`  
 イメージへのポインター。  
  
 `pParent`  
 現在のイメージ エディター ダイアログ ボックスの親ウィンドウへのポインター。  
  
 `nBitsPixel`  
 色深度とも呼びますが単一のピクセルの色を表すために使用されるビットの数。  場合、`nBitsPixel`パラメーターが-1、色深度がで指定されたイメージから派生した、`pBitmap`パラメーター。 既定値は -1 です。  
  
### <a name="return-value"></a>戻り値  
 イメージを変更するをイメージ ポインターを渡す、`CMFCImageEditorDialog`コンス トラクターです。 まず、`DoModal`をモーダル ダイアログ ボックスを開くメソッドです。 ときに、`DoModal`ビットマップには、新しいイメージが含まれています。 メソッドが返されます。  
  
### <a name="remarks"></a>コメント  
  
### <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCImageEditorDialog`クラスです。 この例の一部である、[新しいコントロール サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)
