---
title: UICheckState 列挙体
ms.date: 04/03/2017
f1_keywords:
- afxwinforms/uicheckstate
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
ms.openlocfilehash: 1411e9b7cb088c063e17cc7c59871e5f0b83ad9c
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692503"
---
# <a name="uicheckstate-enumeration"></a>UICheckState 列挙体

コマンドのユーザー インターフェイス項目のチェックの状態について説明します。

### <a name="syntax"></a>構文

```
public enum class
{
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]
   Unchecked,
   Checked,
   Indeterminate
};
```

### <a name="remarks"></a>Remarks

[ICommandUI::Check](icommandui-interface.md#check)ユーザー インターフェイスの項目の状態を説明するこれらの値を使用します。
Windows フォームの使用に関する詳細については、[MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)
