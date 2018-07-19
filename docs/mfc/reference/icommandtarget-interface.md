---
title: ICommandTarget インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
dev_langs:
- C++
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 086b0b1d17d32a747802a8c1df783fb6a20a560e
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339775"
---
# <a name="icommandtarget-interface"></a>ICommandTarget インターフェイス
コマンド ソース オブジェクトからのコマンドを受信するインターフェイスを使用するユーザー コントロールを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ICommandTarget::Initialize](#initialize)|コマンド ターゲット オブジェクトを初期化します。|  
  
## <a name="remarks"></a>Remarks  
 MFC ビューでユーザー コントロールをホストするときに[CWinFormsView](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンド (たとえば、フレームのメニュー項目やツールバーのボタン) を処理できるようにします。 実装することによって`ICommandTarget`、ユーザー コントロールへの参照を提供する、 [ICommandSource](../../mfc/reference/icommandsource-interface.md)オブジェクト。  
  
 参照してください[方法: Windows フォーム コントロールにコマンド ルーティングを追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)を使用する方法の例については`ICommandTarget`します。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  
  
##  <a name="initialize"></a> ICommandTarget::Initialize  
 コマンド ターゲット オブジェクトを初期化します。  
  
```  
void Initialize(ICommandSource^ cmdSource);  
```  
  
### <a name="parameters"></a>パラメーター  
 *cmdSource*  
 コマンド ソース オブジェクトへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 MFC ビューでユーザー コントロールをホストする場合、CWinFormsView は MFC のコマンドを処理することを許可するユーザー コントロールにコマンドおよび更新コマンド UI メッセージをルーティングします。  
  
 このメソッドは、コマンド ターゲット オブジェクトを初期化し、指定したコマンドのソース オブジェクト cmdSource に関連付けます。 ユーザー コントロール クラスの実装で呼び出す必要があります。 初期化時に、呼び出し元の ICommandSource::AddCommandHandler Initialize 実装では、コマンド ソース オブジェクトとコマンド ハンドラーを登録してください。 表示する方法: 初期化を使用してこれを実行する方法の例については、Windows フォーム コントロールにコマンド ルーティングを追加します。  
  
## <a name="see-also"></a>関連項目  
 [方法: コマンドを追加するコントロールをフォーム、Windows へのルーティング](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandSource インターフェイス](../../mfc/reference/icommandsource-interface.md)



