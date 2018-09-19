---
title: CSimpleDialog クラス |Microsoft Docs
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
ms.openlocfilehash: f58efa7b7ba5c0452f2418a2dbbc27c94eedaca6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087956"
---
# <a name="csimpledialog-class"></a>CSimpleDialog クラス

このクラスは、基本的なモーダル ダイアログ ボックスを実装します。

## <a name="syntax"></a>構文

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>パラメーター

*t_wDlgTemplateID*

ダイアログ テンプレート リソースのリソース ID。

*t_bCenter*<br/>
ダイアログ オブジェクトは、オーナー ウィンドウの 中央揃えにする場合は TRUE。それ以外の場合は FALSE です。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleDialog::DoModal](#domodal)|モーダル ダイアログ ボックスを作成します。|

## <a name="remarks"></a>Remarks

基本的な機能を持つモーダル ダイアログ ボックスを実装します。 `CSimpleDialog` Windows のコモン コントロールのみのサポートを提供します。 作成し、モーダル ダイアログ ボックスを表示するには、ダイアログ ボックスの既存のリソース テンプレートの名前を指定する、このクラスのインスタンスを作成します。 (IDOK、IDCANCEL など) の定義済みの値を持つ任意のコントロールをクリックすると、ダイアログ ボックスのオブジェクトを閉じます。

`CSimpleDialog` モーダル ダイアログ ボックスのみを作成することができます。 `CSimpleDialog` メッセージを適切なハンドラーを送信する既定のメッセージ マップを使用して、ダイアログ ボックス プロシージャを提供します。

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

*hWndParent*<br/>
ダイアログ ボックスの親へのハンドル。 値が指定されていない場合は、親が現在アクティブなウィンドウに設定されます。

### <a name="return-value"></a>戻り値

成功した場合、戻り値は、ダイアログ ボックスを閉じているコントロールのリソース ID です。

関数が失敗した場合、戻り値は-1 です。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

### <a name="remarks"></a>Remarks

このメソッドは、ダイアログ ボックスがアクティブな間、ユーザーとすべての対話を処理します。 これにより、ダイアログ ボックスがモーダル; は、します。ユーザーは、ダイアログ ボックスが閉じられるまで、他のウィンドウを操作できません。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
