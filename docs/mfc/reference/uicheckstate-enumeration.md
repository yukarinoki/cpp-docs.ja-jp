---
title: UICheckState 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 04/03/2017
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- afxwinforms/uicheckstate
dev_langs:
- C++
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc09dcb36d7d1ec1abd2f51fd13b6daadd74601f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403852"
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
Windows フォームの使用に関する詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。

### <a name="requirements"></a>要件

**ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)
