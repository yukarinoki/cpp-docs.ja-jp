---
description: 詳細については、「MFC モジュールの状態データの管理」を参照してください。
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
ms.openlocfilehash: e991e73b40f49f3be4630c26957c827aa6f1bf0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228028"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC モジュールの状態データの管理

この記事では、MFC モジュールの状態データについて説明し、実行フロー (実行時にパスコードがアプリケーションを通過する) がモジュールを出入りする場合に、この状態がどのように更新されるかについて説明します。 モジュールの状態を AFX_MANAGE_STATE と METHOD_PROLOGUE マクロに切り替える方法についても説明します。

> [!NOTE]
> ここでの "モジュール" という用語は、実行可能なプログラム、またはアプリケーションの他の部分とは独立して動作する DLL (または dll のセット) を指しますが、MFC DLL の共有コピーを使用します。 ActiveX コントロールは、一般的なモジュールの例です。

次の図に示すように、MFC は、アプリケーションで使用される各モジュールの状態データを保持しています。 このデータの例としては、Windows インスタンスハンドル (リソースの読み込みに使用される)、 `CWinApp` アプリケーションの現在のオブジェクトとオブジェクトへのポインター `CWinThread` 、OLE モジュール参照カウント、および windows オブジェクトハンドルとそれに対応する MFC オブジェクトのインスタンスとの間の接続を維持するさまざまなマップがあります。 ただし、アプリケーションで複数のモジュールを使用する場合、各モジュールの状態データはアプリケーション全体ではなくなります。 各モジュールには、MFC の状態データの独自のプライベートコピーがあります。

![1つのモジュール &#40;アプリケーションの状態データ&#41;](../mfc/media/vc387n1.gif "1つのモジュール &#40;アプリケーションの状態データ&#41;") <br/>
単一モジュール (アプリケーション) の状態データ

モジュールの状態データは構造体に含まれており、常にその構造体へのポインターを介して使用できます。 次の図に示すように、実行のフローが特定のモジュールに入った場合、そのモジュールの状態は "現在" または "有効" の状態である必要があります。 したがって、各スレッドオブジェクトには、そのアプリケーションの有効な状態構造へのポインターがあります。 このポインターを常に更新しておくことは、アプリケーションのグローバル状態を管理し、各モジュールの状態の整合性を維持するために不可欠です。 グローバル状態の管理が正しくないと、予期しないアプリケーションの動作が発生する可能性があります。

![複数のモジュールの状態データ](../mfc/media/vc387n2.gif "複数モジュールの状態データ") <br/>
複数モジュールの状態データ

つまり、各モジュールは、すべてのエントリポイントでモジュールの状態を正しく切り替える必要があります。 "エントリポイント" とは、実行フローがモジュールのコードを入力できる場所です。 エントリポイントは次のとおりです。

- [DLL 内のエクスポート関数](exported-dll-function-entry-points.md)

- [COM インターフェイスのメンバー関数](com-interface-entry-points.md)

- [ウィンドウプロシージャ](window-procedure-entry-points.md)

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](general-mfc-topics.md)
