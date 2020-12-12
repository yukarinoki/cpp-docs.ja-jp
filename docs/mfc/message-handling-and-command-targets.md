---
description: 詳細については、メッセージ処理とコマンドターゲットに関するページを参照してください。
title: メッセージ処理とコマンド ターゲット
ms.date: 11/04/2016
f1_keywords:
- IOleCommandTarget
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
ms.openlocfilehash: 35dc54687c7f3742f72d58f5c84cd274bc8fee09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203290"
---
# <a name="message-handling-and-command-targets"></a>メッセージ処理とコマンド ターゲット

コマンドディスパッチインターフェイスは、 `IOleCommandTarget` コマンドのクエリと実行を行うための単純で拡張可能なメカニズムを定義します。 このメカニズムは、標準のコマンドセットに依存しているため、オートメーションの場合よりも簡単です `IDispatch` 。コマンドの引数がほとんどなく、型情報が含まれていない場合 (コマンド引数の場合は型の安全性も低下します)。

コマンドディスパッチインターフェイスの設計では、各コマンドは、 **GUID** で識別される "コマンドグループ" に属します。 そのため、だれでも新しいグループを定義し、そのグループ内のすべてのコマンドを定義できます。 Microsoft または他のベンダーと連携する必要はありません。 (これは基本的に、オートメーションでの **ディスパッチインターフェイス** と **dispid** と同じ意味です。 ここには重複がありますが、このコマンドルーティングメカニズムはコマンドのルーティングのみを対象としており、自動化ハンドルとして大規模なスクリプト作成やプログラミングを行うことはできません。

`IOleCommandTarget` では、次のシナリオが処理されます。

- オブジェクトをアクティブ化すると、通常はオブジェクトのツールバーだけが表示され、オブジェクトのツールバーには、[ **印刷**]、[ **印刷プレビュー**]、[ **保存**]、[ **新規**]、[ **ズーム**] など、一部のコンテナーコマンドのボタンが表示される場合があります。 (インプレースライセンス認証の標準では、オブジェクトがそのようなボタンをツールバーから削除するか、少なくとも無効にすることをお勧めします。 この設計では、これらのコマンドを有効にし、まだ適切なハンドラーにルーティングできます)。現時点では、オブジェクトがこれらのコマンドをコンテナーにディスパッチするメカニズムはありません。

- アクティブなドキュメントがアクティブなドキュメントコンテナー (Office バインダーなど) に埋め込まれている場合、コンテナーは、 **印刷**、 **ページ設定**、 **プロパティ** などのコマンドを、含まれているアクティブなドキュメントに送信することが必要になる場合があります。

このシンプルなコマンドルーティングは、既存のオートメーション標準およびを使用して処理でき `IDispatch` ます。 ただし、に伴うオーバーヘッドは、ここでは必要以上に複雑である `IDispatch` ため、 `IOleCommandTarget` 同じ終了を実現するためのより簡単な方法が用意されています。

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

`QueryStatus`このメソッドは、特定のコマンドセット ( **GUID** で識別されるセット) がサポートされているかどうかをテストします。 この呼び出しでは、サポートされているコマンドの一覧と共に **OLECMD** values (構造体) の配列を設定し、コマンドやステータス情報の名前を説明するテキストを返します。 呼び出し元がコマンドを呼び出す必要がある場合は、コマンド (および set **GUID**) をに渡して、 `Exec` オプションや引数と共に戻り値を取得することができます。

## <a name="see-also"></a>関連項目

[Active ドキュメントコンテナー](active-document-containers.md)
