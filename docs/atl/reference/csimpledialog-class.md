---
title: クラス
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
ms.openlocfilehash: 345372d71ad96a74bb0ae6dd7e89bdf0724cd822
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330828"
---
# <a name="csimpledialog-class"></a>クラス

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
ダイアログ オブジェクトをオーナー ウィンドウの中央に配置する場合は TRUE。それ以外の場合は FALSE。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ::Doモーダル](#domodal)|モーダル ダイアログ ボックスを作成します。|

## <a name="remarks"></a>解説

基本機能を備えたモーダル ダイアログ ボックスを実装します。 `CSimpleDialog`Windows コモン コントロールのサポートのみを提供します。 モーダル ダイアログ ボックスを作成して表示するには、このクラスのインスタンスを作成し、ダイアログ ボックスの既存のリソース テンプレートの名前を指定します。 ダイアログ ボックス オブジェクトは、ユーザーが定義済みの値 (IDOK や IDCANCEL など) を持つコントロールをクリックすると閉じます。

`CSimpleDialog`では、モーダル ダイアログ ボックスのみを作成できます。 `CSimpleDialog`には、既定のメッセージ マップを使用してメッセージを適切なハンドラーに送信するダイアログ ボックス プロシージャが用意されています。

詳細については、「[ダイアログ ボックスの実装](../../atl/implementing-a-dialog-box.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="csimpledialogdomodal"></a><a name="domodal"></a>ダイアログ::Doモーダル

モーダル ダイアログ ボックスを呼び出し、完了時にダイアログ ボックスの結果を返します。

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
ダイアログ ボックスの親へのハンドル。 値が指定されていない場合、親は現在アクティブなウィンドウに設定されます。

### <a name="return-value"></a>戻り値

成功した場合、戻り値はダイアログ ボックスを閉じ、コントロールのリソース ID です。

関数が失敗した場合、戻り値は -1 です。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

### <a name="remarks"></a>解説

このメソッドは、ダイアログ ボックスがアクティブな間、ユーザーとのすべての操作を処理します。 これがダイアログ ボックスをモーダルにするものです。つまり、ダイアログ ボックスが閉じられるまで、他のウィンドウと対話することはできません。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
