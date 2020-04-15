---
title: MFC モジュールの状態データの管理
ms.date: 11/19/2018
helpviewer_keywords:
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
ms.openlocfilehash: c8e79f54ed586201a7d82327662643a9a241b8f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357269"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC モジュールの状態データの管理

この資料では、MFC モジュールの状態データについて説明し、実行フロー (実行時にアプリケーションを通過するパス コード) がモジュールに出入りするときに、この状態がどのように更新されるかについて説明します。 モジュールの状態をAFX_MANAGE_STATEとMETHOD_PROLOGUEマクロで切り替えることも説明します。

> [!NOTE]
> ここでの "モジュール" という用語は、実行可能プログラム、またはアプリケーションの他の部分とは独立して動作する DLL (または DLL のセット) を指しますが、MFC DLL の共有コピーを使用します。 ActiveX コントロールは、モジュールの典型的な例です。

次の図に示すように、MFC にはアプリケーションで使用される各モジュールの状態データがあります。 このデータの例としては、Windows インスタンス ハンドル (リソースの読み込`CWinApp`みに`CWinThread`使用) 、アプリケーションの現在のオブジェクトとオブジェクトへのポインター、OLE モジュール参照カウント、Windows オブジェクト ハンドルと MFC オブジェクトの対応するインスタンス間の接続を維持するさまざまなマップなどがあります。 ただし、アプリケーションが複数のモジュールを使用する場合、各モジュールの状態データはアプリケーション全体ではありません。 むしろ、各モジュールは MFC の状態データの独自のプライベート コピーを持っています。

![アプリケーション&#41;の単一モジュール&#40;状態データ](../mfc/media/vc387n1.gif "アプリケーション&#41;&#40;単一モジュールの状態データ") <br/>
単一モジュール (アプリケーション) の状態データ

モジュールの状態データは構造体に含まれ、その構造体へのポインタを介して常に利用できます。 次の図に示すように、実行フローが特定のモジュールに入るとき、そのモジュールの状態は「現在」または「有効」状態でなければなりません。 したがって、各スレッド オブジェクトには、そのアプリケーションの有効な状態構造へのポインターがあります。 このポインタを常に更新しておくと、アプリケーションのグローバル状態を管理し、各モジュールの状態の整合性を維持するために不可欠です。 グローバル状態の不適切な管理は、予測できないアプリケーションの動作につながる可能性があります。

![複数モジュールの状態データ](../mfc/media/vc387n2.gif "複数モジュールの状態データ") <br/>
複数モジュールの状態データ

つまり、各モジュールは、すべてのエントリ ポイントでモジュールの状態を正しく切り替える役割を担います。 「エントリポイント」とは、実行フローがモジュールのコードに入る任意の場所です。 エントリ ポイントには、次のものがあります。

- [DLL にエクスポートされた関数](../mfc/exported-dll-function-entry-points.md)

- [COM インターフェイスのメンバー関数](../mfc/com-interface-entry-points.md)

- [ウィンドウプロシージャ](../mfc/window-procedure-entry-points.md)

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
