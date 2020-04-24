---
title: インターフェイス
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: be64f4e0367b9ecc1b24fa96f067f4acd45a9978
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751457"
---
# <a name="icommandtarget-interface"></a>インターフェイス

コマンド ソース オブジェクトからコマンドを受け取るインターフェイスを持つユーザー コントロールを提供します。

## <a name="syntax"></a>構文

```
interface class ICommandTarget
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[I コマンドターゲット::初期化](#initialize)|コマンド ターゲット オブジェクトを初期化します。|

## <a name="remarks"></a>解説

MFC ビューでユーザー コントロールをホストすると[、CWinFormsView](../../mfc/reference/cwinformsview-class.md)コマンドをルーティングし、コマンド UI メッセージをユーザー コントロールに更新して、MFC コマンド (フレーム メニュー項目やツール バー ボタンなど) を処理できるようにします。 を実装`ICommandTarget`すると、ユーザー コントロールに[ICommandSource](../../mfc/reference/icommandsource-interface.md)オブジェクトへの参照を与えます。

の使用方法`ICommandTarget`の例については、「[方法 : Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)」を参照してください。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="icommandtargetinitialize"></a><a name="initialize"></a>I コマンドターゲット::初期化

コマンド ターゲット オブジェクトを初期化します。

```cpp
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>パラメーター

*コマンドソース*<br/>
コマンド ソース オブジェクトへのハンドル。

### <a name="remarks"></a>解説

MFC ビューでユーザー コントロールをホストすると、コマンドが CWinFormsView によってコマンドのルーティングと更新コマンド UI メッセージがユーザー コントロールに転送され、MFC コマンドを処理できるようになります。

このメソッドは、コマンド ターゲット オブジェクトを初期化し、指定したコマンド ソース オブジェクト cmdSource に関連付けます。 これは、ユーザー コントロール クラスの実装で呼び出す必要があります。 初期化時に、Initialize 実装で ICommandSource::AddCommandHandler を呼び出してコマンド ソース オブジェクトにコマンド ハンドラーを登録する必要があります。 初期化を使用してこれを行う方法の例については、「方法: Windows フォーム コントロールへのコマンド ルーティングの追加」を参照してください。

## <a name="see-also"></a>関連項目

[方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[インターフェイス](../../mfc/reference/icommandsource-interface.md)
