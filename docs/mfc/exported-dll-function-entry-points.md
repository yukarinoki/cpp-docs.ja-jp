---
title: DLL 関数のエントリ ポイントをエクスポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1be4c74a48f1367369582b433a2a833ceb8e1976
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="exported-dll-function-entry-points"></a>DLL のエクスポート関数のエントリ ポイント
DLL のエクスポート関数を使用して、 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) DLL モジュールから呼び出し元のアプリケーションの DLL に切り替える際に、適切なグローバル状態を維持するためにマクロです。  
  
 呼び出されると、このマクロは、設定`pModuleState`へのポインター、`AFX_MODULE_STATE`関数のスコープの残りの有効なモジュールの状態と、モジュール用グローバル データを含む構造体。 マクロを含むスコープから離れると、以前の有効なモジュールの状態が自動的に復元します。  
  
 インスタンスを構築することによってこの切り替えを行う、 **AFX_MODULE_STATE**スタック上のクラスです。 コンス トラクターにこのクラス現在のモジュール状態へのポインターを取得し、メンバー変数に格納し、設定`pModuleState`新しい有効なモジュールの状態とします。 デストラクターの中では、このクラスは、有効なモジュールの状態とそのメンバー変数に格納されているポインターを復元します。  
  
 いずれかの DLL のダイアログ ボックスを起動するなど、エクスポートされた関数がある場合は、関数の先頭に次のコードを追加する必要があります。  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]  
  
 モジュールの現在の状態から返された状態と交換この[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)現在のスコープが終了するまでです。  
  
 Dll のリソースに問題が発生する場合、`AFX_MANAGE_STATE`マクロは使用されません。 既定では、MFC では、メイン アプリケーションのリソース ハンドルを使用して、リソース テンプレートを読み込みます。 このテンプレートは、DLL に実際に格納されます。 根本原因がで MFC のモジュールの状態情報が切り替えられましたいないこと、`AFX_MANAGE_STATE`マクロです。 リソース ハンドルは、MFC のモジュールの状態から回復しました。 モジュールの状態が切り替えられていないすると、間違ったリソース ハンドルが使用されます。  
  
 `AFX_MANAGE_STATE` DLL 内の各関数に挿入する必要はありません。 たとえば、`InitInstance`せず、アプリケーションで MFC コードから呼び出すことが`AFX_MANAGE_STATE`MFC する前にモジュールの状態を自動的に移動するため`InitInstance`と後、再度スイッチ、`InitInstance`を返します。 すべてのメッセージ マップ ハンドラー同様です。 正規の MFC Dll には、実際には、すべてのメッセージをルーティングする前にモジュールの状態は自動的に切り替わりますマスターの特殊なウィンドウ プロシージャがあり。  
  
## <a name="see-also"></a>関連項目  
 [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)

