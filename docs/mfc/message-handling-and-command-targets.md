---
title: メッセージの処理とコマンド ターゲット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7184a6e8df67dfd220173c42bfa3e0580bd2cd3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="message-handling-and-command-targets"></a>メッセージ処理とコマンド ターゲット
コマンドのディスパッチ インターフェイス`IOleCommandTarget`クエリおよびコマンドを実行する単純で拡張可能なメカニズムを定義します。 このメカニズムは、Automation のよりも簡単`IDispatch`コマンドの引数を持つことはほとんどありませんコマンドの標準セットに完全に依存しているためと、型情報は必要ありません (タイプ セーフはコマンドの引数も低下)。  
  
 コマンドのディスパッチ インターフェイスのデザインで各コマンド グループに属している、"コマンド"は、それ自体で識別される、 **GUID**です。 したがって、新しいグループを定義でき、Microsoft と連携するすべての必要性や、他のベンダーなしには、そのグループ内のすべてのコマンドを定義するすべてのユーザーができます。 (これは、本質的には、同じ手段として定義、 **dispinterface** plus **Dispid** Automation でします。 オーバー ラップがあるここでは、このコマンド ルーティング メカニズムはコマンド ルーティングにのみ、大規模な環境でのスクリプティング/プログラミングではなくオートメーションのハンドルとしてです。)  
  
 `IOleCommandTarget` 次のシナリオを処理します。  
  
-   オブジェクトが、インプレース アクティブ化、通常は、オブジェクトのツールバーを表示し、オブジェクトのツールバーでは、いくつかのようにコンテナーのコマンドのボタンがあります専用**印刷**、**印刷プレビュー**、 **保存**、 `New`、**ズーム**、およびその他。 (インプレースのアクティブ化の標準の推奨オブジェクトを削除するにまたは、ツールバーからこのようなボタンは、少なくとも無効にします。 この設計でそれらのコマンドを有効にし、右側のハンドラーにまだルーティングされます。)現時点では、オブジェクトをコンテナーにこれらのコマンドをディスパッチするためのメカニズムはありません。  
  
-   コマンドを送信するこのようなコンテナーが必要があります (Office バインダー) などの active ドキュメント コンテナーでは、アクティブなドキュメントが埋め込まれているときに**印刷**、**ページ セットアップ**、**プロパティ**、およびその他のユーザーが含まれているアクティブなドキュメントです。  
  
 既存のオートメーション標準を介して処理することがこの単純なコマンド ルーティングおよび`IDispatch`です。 ただし、オーバーヘッドに含まれている`IDispatch`は、ここでは、必要に応じてより多くなってように`IOleCommandTarget`は、同じ結果を実現するためにシンプルな手段を提供します。  
  
```  
interface IOleCommandTarget : IUnknown  
    {  
    HRESULT QueryStatus(  
        [in] GUID *pguidCmdGroup,  
        [in] ULONG cCmds,  
        [in,out][size_is(cCmds)] OLECMD *prgCmds,  
        [in,out] OLECMDTEXT *pCmdText);  
    HRESULT Exec(  
        [in] GUID *pguidCmdGroup,  
        [in] DWORD nCmdID,  
        [in] DWORD nCmdExecOpt,  
        [in] VARIANTARG *pvaIn,  
        [in,out] VARIANTARG *pvaOut);  
    }  
```  
  
 `QueryStatus`メソッドをここでは、特定の一連のコマンド セットで識別されるかどうかを検査、 **GUID**はサポートされています。 この呼び出しの配列に格納**OLECMD**コマンドだけでなく、コマンドまたは状態情報の名前を記述するテキストを返すのサポートされている一覧の値 (構造体)。 コマンドを渡すことができます、呼び出し元がコマンドを呼び出すしようとすると、ときに (とセット**GUID**) に**Exec**オプションと引数、と共に値を取得戻り値。  
  
## <a name="see-also"></a>関連項目  
 [Active ドキュメント コンテナー](../mfc/active-document-containers.md)

