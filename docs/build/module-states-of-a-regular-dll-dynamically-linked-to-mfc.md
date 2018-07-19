---
title: 正規の MFC DLL のモジュールの状態は、MFC と動的にリンク |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d15f533473ebe90d6d105ddeb57dcdcddd90e87b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369371"
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>正規の MFC DLL のモジュールの状態は、MFC と動的にリンク
MFC DLL に標準 MFC DLL を動的にリンクする機能は、非常に複雑になっているいくつかの構成を許可します。 たとえば、標準 MFC DLL とそれを使用する実行可能ファイル両方動的にリンクできます MFC DLL にし、任意の MFC 拡張 Dll にします。  
  
 この構成が現在へのポインターなど、MFC のグローバル データに関して問題によって引き起こされる`CWinApp`オブジェクトおよびハンドル マップします。  
  
 MFC version 4.0 では、前に、このグローバル データは、MFC DLL 内にありされ、プロセスのすべてのモジュールで共有されていました。 Win32 DLL を使用する各プロセスが独自の DLL のデータのコピーを取得するため、このスキームには、プロセスごとのデータを追跡する簡単な方法が用意されています。 また、AFXDLL モデルが疑われる場合があることが 1 つだけため`CWinApp`オブジェクトと 1 つだけの一連の処理、プロセス内の対応付け、MFC DLL 自体でこれらの項目を追跡する可能性があります。  
  
 MFC DLL に MFC 標準 DLL を動的にリンクすること、これで 2 つ以上を設定することが`CWinApp`プロセス内のオブジェクト: およびハンドルのマップの 2 つ以上のセットもします。 方法は MFC の追跡を使用している必要がありますどれですか。  
  
 ソリューションでは、このグローバル状態情報のコピーを各モジュール (アプリケーションまたはレギュラー MFC DLL) に、です。 したがってへの呼び出し**AfxGetApp**標準では、MFC の DLL はへのポインターを返します。、`CWinApp`実行可能ファイルのものではなく、DLL 内のオブジェクト。 MFC のグローバル データの場合は、このモジュールのコピーはモジュールの状態と呼ばれます、、「 [MFC テクニカル ノート 58](../mfc/tn058-mfc-module-state-implementation.md)です。  
  
 正規の MFC DLL に実装されているすべてのメッセージ ハンドラーで心配する必要はありません、MFC の一般的なウィンドウ プロシージャは自動的に適切なモジュールの状態に切り替わります。 実行可能ファイルを呼び出したときに、正規の MFC DLL は、DLL のいずれかに現在のモジュール状態を明示的に設定する必要があります。 これを行うを使用して、 **AFX_MANAGE_STATE**マクロですべての関数は DLL からエクスポートします。 これは、DLL からエクスポートされた関数の先頭に次のコード行を追加することによって行います。  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [MFC モジュールの状態データを管理します。](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [MFC と動的にリンクされている標準の MFC Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC 拡張 DLL](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)