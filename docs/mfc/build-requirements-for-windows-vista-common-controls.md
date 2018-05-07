---
title: Windows Vista コモン コントロールの作成要件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08d86af5f54fb9dfe81327b4589d60e5290b2610
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Windows Vista コモン コントロールの作成要件
Microsoft Foundation Class (MFC) ライブラリには、Windows のコモン コントロール バージョン 6.1 がサポートしています。 一般的なコントロールが含まれている[!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]にライブラリが含まれています、[!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)]です。 ライブラリをサポートするメソッドと、既存のクラス、および新しいクラスを強化する新しいメソッドを提供する[!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]コモン コントロールです。 アプリケーションをビルドすると、次のセクションで説明されている、コンパイルと移行の要件に従ってください。  
  
## <a name="compilation-requirements"></a>コンパイル要件  
  
### <a name="supported-versions"></a>サポートされているバージョン  
 いくつかの新しいクラスとメソッドだけをサポートして[!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]以降、他のメソッドも以前のオペレーティング システムをサポートします。 内のメモ、`Requirements`メソッドの各トピックのセクションでは、ときに、最低限必要なオペレーティング システムを指定[!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]です。  
  
 お使いのコンピューターが実行されない場合でも[!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]で実行される MFC アプリケーションをビルドする[!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]バージョン 6.1 MFC ヘッダー ファイルがコンピューターにある場合。 ただし、一般的なコントロール専用に設計された[!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)]そのシステムでのみ動作し、以前のオペレーティング システムでは無視されます。  
  
### <a name="supported-character-sets"></a>サポートされている文字セット  
 新しい Windows コモン コントロールは、のみ、Unicode 文字セットと ANSI 文字セットではなくをサポートします。 コマンドラインでアプリケーションをビルドする場合は、次の定義の両方を使用 (/D) 文字セットの基になるとして Unicode を指定するコンパイラ オプション。  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Visual Studio 統合開発環境 (IDE) でアプリケーションをビルドする場合は、指定、 **Unicode 文字セットを**のオプション、**文字セット**プロパティに、**全般**プロジェクトのプロパティのノードです。  
  
 ANSI バージョンのいくつかの MFC メソッドは、Windows のコモン コントロール バージョン 6.1 以降で廃止されました。 詳細については、次を参照してください。 [ANSI Api の廃止](../mfc/deprecated-ansi-apis.md)です。  
  
## <a name="migration-requirements"></a>移行の要件  
 Windows コモン コントロール バージョン 6.1 を使用する新しい MFC アプリケーションをビルドする Visual Studio IDE を使用する場合、IDE は自動的に適切なマニフェストを宣言します。 ただし、以前のバージョンの Visual Studio から既存の MFC アプリケーションを移行する、新しいコモン コントロールを使用する場合は、IDE は自動的に提供されませんマニフェスト情報をアプリケーションをアップグレードします。 Stdafx.h ファイルに次のソース コードを手動で挿入する必要があります。  
  
```  
#ifdef UNICODE  
#if defined _M_IX86  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_IA64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_X64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#else  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#endif  
#endif  
```  
  
## <a name="see-also"></a>関連項目  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [階層図](../mfc/hierarchy-chart.md)   
 
  [非推奨の ANSI API](../mfc/deprecated-ansi-apis.md)

