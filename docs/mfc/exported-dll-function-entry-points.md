---
title: DLL のエクスポート関数のエントリ ポイント
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
ms.openlocfilehash: c521cad666864c728fd871b460cf0c92b815e414
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622641"
---
# <a name="exported-dll-function-entry-points"></a>DLL のエクスポート関数のエントリ ポイント

DLL のエクスポート関数の場合は、DLL モジュールから呼び出し元のアプリケーションの DLL に切り替えるときに、 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)マクロを使用して、適切なグローバル状態を維持します。

このマクロが呼び出されると、 `pModuleState` モジュールのグローバルデータを格納している構造体へのポインターが、その `AFX_MODULE_STATE` 関数の格納スコープの残りの部分の有効なモジュール状態として設定されます。 マクロを含むスコープを離れると、以前の有効なモジュールの状態が自動的に復元されます。

この切り替えは、スタック上のクラスのインスタンスを構築することによって実現され `AFX_MODULE_STATE` ます。 コンストラクターでは、このクラスは現在のモジュールの状態へのポインターを取得し、それをメンバー変数に格納した後、 `pModuleState` 新しい有効なモジュールの状態としてを設定します。 デストラクターでは、このクラスは、メンバー変数に格納されているポインターを、有効なモジュール状態として復元します。

DLL 内のダイアログボックスを起動する関数など、エクスポートされた関数がある場合は、関数の先頭に次のコードを追加する必要があります。

[!code-cpp[NVC_MFCConnectionPoints#6](codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]

これにより、現在のモジュールの状態が、現在のスコープの末尾まで[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)から返された状態と交換されます。

マクロが使用されていない場合、Dll 内のリソースに関する問題が発生 `AFX_MANAGE_STATE` します。 既定では、MFC はメインアプリケーションのリソースハンドルを使用して、リソーステンプレートを読み込みます。 このテンプレートは、実際には DLL に格納されています。 根本的な原因は、MFC のモジュール状態情報がマクロによって切り替えられていないことです `AFX_MANAGE_STATE` 。 リソースハンドルは、MFC のモジュール状態から回復されます。 モジュールの状態を切り替えないと、正しくないリソースハンドルが使用されます。

`AFX_MANAGE_STATE`は、DLL 内のすべての関数に配置する必要はありません。 たとえば、は `InitInstance` アプリケーションの mfc コードによって呼び出すことができ `AFX_MANAGE_STATE` ます。これは、mfc がモジュールの状態を自動的にシフト `InitInstance` してから制御が戻った後に再び切り替えるため `InitInstance` です。 すべてのメッセージマップハンドラーにも同じことが当てはまります。 通常の MFC Dll には、メッセージをルーティングする前にモジュールの状態を自動的に切り替える特別なマスターウィンドウプロシージャがあります。

## <a name="see-also"></a>関連項目

[MFC モジュールの状態データの管理](managing-the-state-data-of-mfc-modules.md)
