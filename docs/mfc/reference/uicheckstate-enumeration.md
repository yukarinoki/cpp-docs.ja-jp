---
description: '詳細については、次を参照してください: UICheckState 列挙型'
title: UICheckState 列挙体
ms.date: 04/03/2017
f1_keywords:
- afxwinforms/uicheckstate
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
ms.openlocfilehash: 8c6f250dd6f6646d22aac0fa819b73537ee0f443
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218642"
---
# <a name="uicheckstate-enumeration"></a>UICheckState 列挙体

コマンドのユーザーインターフェイス項目のチェックの状態を記述します。

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

### <a name="remarks"></a>解説

[ICommandUI:: Check](icommandui-interface.md#check) は、これらの値を使用して、ユーザーインターフェイス項目の状態を表します。
Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

### <a name="requirements"></a>要件

**ヘッダー:** afxwinforms (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)
