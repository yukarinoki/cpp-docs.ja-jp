---
description: '詳細情報: CSimpleDialog クラス'
title: CSimpleDialog クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: 50889c4387515c85cd3c6e53bf12e7c0494504ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140648"
---
# <a name="csimpledialog-class"></a>CSimpleDialog クラス

このクラスは、基本的なモーダルダイアログボックスを実装します。

## <a name="syntax"></a>構文

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>パラメーター

*t_wDlgTemplateID*

ダイアログテンプレートリソースのリソース ID。

*t_bCenter*<br/>
ダイアログオブジェクトをオーナーウィンドウの中央に配置する場合は TRUE。それ以外の場合は FALSE。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleDialog::D oModal](#domodal)|モーダルダイアログボックスを作成します。|

## <a name="remarks"></a>解説

基本機能を備えたモーダルダイアログボックスを実装します。 `CSimpleDialog` では、Windows コモンコントロールのみがサポートされます。 モーダルダイアログボックスを作成して表示するには、このクラスのインスタンスを作成し、ダイアログボックスの既存のリソーステンプレートの名前を指定します。 ユーザーが定義済みの値 (IDOK や IDCANCEL など) を使用してコントロールをクリックすると、ダイアログボックスオブジェクトが閉じます。

`CSimpleDialog` モーダルダイアログボックスのみを作成できます。 `CSimpleDialog` 既定のメッセージマップを使用してメッセージを適切なハンドラーに送信するダイアログボックスの手順を示します。

詳細について [は、「ダイアログボックスの実装](../../atl/implementing-a-dialog-box.md) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="csimpledialogdomodal"></a><a name="domodal"></a> CSimpleDialog::D oModal

モーダルダイアログボックスを呼び出し、完了したときにダイアログボックスの結果を返します。

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
ダイアログボックスの親へのハンドル。 値が指定されていない場合、親は現在のアクティブウィンドウに設定されます。

### <a name="return-value"></a>戻り値

成功した場合、戻り値は、ダイアログボックスを閉じたコントロールのリソース ID になります。

関数が失敗した場合、戻り値は-1 になります。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

### <a name="remarks"></a>解説

このメソッドは、ダイアログボックスがアクティブなときに、ユーザーとのすべての対話を処理します。 これにより、ダイアログボックスがモーダルになります。つまり、ダイアログボックスが閉じられるまで、ユーザーは他のウィンドウと対話できません。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
