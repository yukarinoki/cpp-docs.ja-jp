---
title: Windows Vista コモン コントロールの作成要件
ms.date: 11/04/2016
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
ms.openlocfilehash: c9a01665339c28b58a5d528cbb9dfaa235e7f1ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637074"
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Windows Vista コモン コントロールの作成要件

Microsoft Foundation Class (MFC) ライブラリでは、Windows のコモン コントロール バージョン 6.1 をサポートします。 Windows Vista のコモン コントロールが含まれているし、ライブラリは、Visual Studio SDK に含まれます。 ライブラリは、既存のクラス、および新しいクラスを強化する新しいメソッドと Windows Vista コモン コントロールをサポートするメソッドを提供します。 アプリケーションをビルドするときに、次のセクションで説明されている、コンパイルと移行の要件に従ってください。

## <a name="compilation-requirements"></a>コンパイルの要件

### <a name="supported-versions"></a>サポートされているバージョン

Windows Vista のみをサポートし、後で、その他の中にいくつかの新しいクラスとメソッドのメソッドも以前のオペレーティング システムをサポートします。 内のメモ、`Requirements`各メソッドのトピックのセクションでは、最低限に必要なオペレーティング システムが Windows Vista を指定します。

コンピューターが Windows Vista が実行されない場合でも、コンピューターにバージョン 6.1 MFC ヘッダー ファイルがある場合は、Windows Vista で実行される MFC アプリケーションを構築できます。 ただし、具体的には Windows Vista 用に設計された一般的なコントロールは、そのシステムでのみ動作し、以前のオペレーティング システムでは無視されます。

### <a name="supported-character-sets"></a>サポートされている文字セット

新しい Windows コモン コントロールでは、Unicode 文字セットのみと ANSI 文字セットではなくをサポートします。 コマンドラインでアプリケーションをビルドする場合は、次の定義の両方を使用 (/D) 文字セットの基になる Unicode を指定するコンパイラ オプション。

```
/D_UNICODE /DUNICODE
```

Visual Studio 統合開発環境 (IDE) でアプリケーションをビルドする場合は、指定、 **Unicode 文字セットを**のオプション、**文字セット**プロパティ、**全般**プロジェクトのプロパティのノード。

Windows コモン コントロール バージョン 6.1 以降、ANSI バージョンのいくつかの MFC メソッドを推奨されていませんが。 詳細については、次を参照してください。[非推奨の ANSI Api](../mfc/deprecated-ansi-apis.md)します。

## <a name="migration-requirements"></a>移行の要件

Windows コモン コントロール バージョン 6.1 を使用する新しい MFC アプリケーションをビルドする Visual Studio IDE を使用する場合、IDE は、適切なマニフェストを自動的に宣言します。 ただし、以前のバージョンの Visual Studio から既存の MFC アプリケーションを移行する、新しいコモン コントロールを使用する場合は、IDE に自動的には説明しませんマニフェストでアプリケーションをアップグレードします。 代わりで次のソース コードを挿入する必要があります手動で、 **stdafx.h**ファイル。

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

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[階層図](../mfc/hierarchy-chart.md)<br/>
[非推奨の ANSI API](../mfc/deprecated-ansi-apis.md)

