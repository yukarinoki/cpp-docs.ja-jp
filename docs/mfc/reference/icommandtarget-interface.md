---
description: 詳細については、「ICommandTarget インターフェイス」を参照してください。
title: ICommandTarget インターフェイス
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: 6deb11ecca94160ea19225fb955826845a4cdefa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219578"
---
# <a name="icommandtarget-interface"></a>ICommandTarget インターフェイス

コマンドソースオブジェクトからコマンドを受信するためのインターフェイスをユーザーコントロールに提供します。

## <a name="syntax"></a>構文

```
interface class ICommandTarget
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ICommandTarget:: Initialize](#initialize)|コマンドターゲットオブジェクトを初期化します。|

## <a name="remarks"></a>解説

MFC ビューでユーザーコントロールをホストすると、 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) はコマンドをルーティングし、コマンド UI メッセージをユーザーコントロールに送信して、mfc コマンドを処理できるようにします (たとえば、フレームのメニュー項目やツールバーのボタンなど)。 を実装することにより、 `ICommandTarget` ユーザーコントロールに [ICommandSource](../../mfc/reference/icommandsource-interface.md) オブジェクトへの参照を提供します。

の使用方法の例については [、「方法: Windows フォームコントロールにコマンドルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 」を参照してください `ICommandTarget` 。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** afxwinforms (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="icommandtargetinitialize"></a><a name="initialize"></a> ICommandTarget:: Initialize

コマンドターゲットオブジェクトを初期化します。

```cpp
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>パラメーター

*cmdSource*<br/>
コマンドソースオブジェクトへのハンドル。

### <a name="remarks"></a>解説

MFC ビューでユーザーコントロールをホストすると、CWinFormsView はコマンドをルーティングし、ユーザーコントロールにコマンド UI メッセージを更新して、MFC コマンドを処理できるようにします。

このメソッドは、コマンドターゲットオブジェクトを初期化し、指定したコマンドソースオブジェクト cmdSource に関連付けます。 これは、ユーザーコントロールクラスの実装で呼び出される必要があります。 初期化では、Initialize 実装で ICommandSource:: AddCommandHandler を呼び出すことによって、コマンドハンドラーをコマンドソースオブジェクトに登録する必要があります。 Initialize を使用してこれを行う方法の例については、「方法: Windows フォームコントロールにコマンドルーティングを追加する」を参照してください。

## <a name="see-also"></a>関連項目

[方法: Windows フォームコントロールにコマンドルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandSource インターフェイス](../../mfc/reference/icommandsource-interface.md)
