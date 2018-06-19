---
title: CWinFormsView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd0af17faf3eb4a7206f50d81753e1def508aed4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370550"
---
# <a name="cwinformsview-class"></a>CWinFormsView クラス
Windows フォーム コントロールのホスティング用の汎用機能を MFC ビューとして提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|`CWinFormsView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsView::GetControl](#getcontrol)|Windows フォーム コントロールへのポインターを取得します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前||  
|----------|-|  
|[CWinFormsView::operator コントロール ^](#operator_control)|Windows フォーム コントロールへのポインターとして型をキャストします。|  
  
## <a name="remarks"></a>コメント  
 MFC を使用して、 `CWinFormsView` MFC ビュー内で .NET Framework の Windows フォーム コントロールをホストするクラス。 コントロールは、ネイティブのビューの子であるし、MFC ビューの全体のクライアント領域を占有します。 結果がに似ていますが、`CFormView`ビュー、Windows フォーム デザイナーを利用し、実行時に豊富なフォーム ベースのビューを作成することができます。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
> [!NOTE]
>  MFC Windows フォームの統合は、MFC と動的にリンクするプロジェクトでのみ動作 (プロジェクトの AFXDLL が定義されている場合)。  
  
> [!NOTE]
>  CWinFormsView は MFC 分割ウィンドウをサポートしていません ( [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md))。 現在のみ、Windows フォームのスプリッター コントロールはサポートされています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h  
  
##  <a name="cwinformsview"></a>  CWinFormsView::CWinFormsView  
 `CWinFormsView` オブジェクトを構築します。  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pManagedViewType`  
 Windows フォーム ユーザー コントロールのデータ型へのポインター。   
  
### <a name="example"></a>例  
 次の例で、`CUserView`クラスから継承`CWinFormsView`の型を渡すと`UserControl1`を`CWinFormsView`コンス トラクターです。 `UserControl1` ControlLibrary1.dll でカスタム コントロールです。  
  
 [!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="getcontrol"></a>  CWinFormsView::GetControl  
 Windows フォーム コントロールへのポインターを取得します。  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`System.Windows.Forms.Control`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 Windows フォームを使用する方法の例は、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
##  <a name="operator_control"></a>  CWinFormsView::operator コントロール ^  
 Windows フォーム コントロールへのポインターとして型をキャストします。  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>コメント  
 この演算子は、渡すことができます、`CWinFormsView`型の Windows フォーム コントロールへのポインターを受け取る関数をビュー<xref:System.Windows.Forms.Control>です。  
  
### <a name="example"></a>例  
  参照してください[CWinFormsView::GetControl](#getcontrol)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数クラス](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)
