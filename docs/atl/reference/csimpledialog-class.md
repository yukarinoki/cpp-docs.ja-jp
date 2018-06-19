---
title: CSimpleDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3a8f6cb2ead8798b86d65a1fa875a42a68cdd77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362388"
---
# <a name="csimpledialog-class"></a>CSimpleDialog クラス
このクラスは、基本のモーダル ダイアログ ボックスを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>パラメーター  
 *t_wDlgTemplateID*  
  
 ダイアログ テンプレート リソースのリソース ID です。  
  
 *t_bCenter*  
 **TRUE**ダイアログ オブジェクトする場合は、オーナー ウィンドウの中央に配置します。 それ以外の**FALSE**です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|モーダル ダイアログ ボックスを作成します。|  
  
## <a name="remarks"></a>コメント  
 基本的な機能を持つモーダル ダイアログ ボックスを実装します。 `CSimpleDialog` Windows コモン コントロールのみのサポートを提供します。 作成、モーダル ダイアログ ボックスを表示するには、ダイアログ ボックスの既存のリソース テンプレートの名前を提供する、このクラスのインスタンスを作成します。 ユーザー (IDOK、IDCANCEL など) の定義済みの値を持つ任意のコントロールがクリックしたときに、ダイアログ ボックスのオブジェクトを閉じます。  
  
 `CSimpleDialog` モーダル ダイアログ ボックスのみを作成できます。 `CSimpleDialog` 既定のメッセージ マップを使用して、適切なハンドラーへのメッセージを送信するためのダイアログ ボックス プロシージャを提供します。  
  
 参照してください[ ダイアログ ボックスを実装する](../../atl/implementing-a-dialog-box.md)詳細についてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="domodal"></a>  CSimpleDialog::DoModal  
 モーダル ダイアログ ボックスの呼び出しを完了ダイアログ ボックスの結果を返します。  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 ダイアログ ボックスの親へのハンドル。 値が指定されていない場合は、親が現在アクティブなウィンドウに設定されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、戻り値は、ダイアログ ボックスを閉じて、コントロールのリソース ID です。  
  
 関数が失敗した場合、戻り値は-1 です。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ダイアログ ボックスがアクティブな間に、ユーザーとすべての対話を処理します。 モーダル ダイアログ ボックスは、します。ユーザーは、ダイアログ ボックスが閉じられるまで、他のウィンドウを操作できません。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
