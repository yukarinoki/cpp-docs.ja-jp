---
title: Windows コモンコントロールのビルド要件
ms.date: 08/19/2019
helpviewer_keywords:
- Common Controls (MFC), build requirements
- Common Controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
ms.openlocfilehash: cf2139e04d2f72feb7951010caa351d67ccc5a93
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619739"
---
# <a name="build-requirements-for-windows-common-controls"></a>Windows コモンコントロールのビルド要件

MFC (Microsoft Foundation Class) ライブラリでは、 [Windows コモンコントロール](/windows/win32/controls/common-controls-intro)がサポートされています。 コモンコントロールは Windows に含まれており、ライブラリは Visual Studio に含まれています。 MFC ライブラリには、既存のクラスを強化する新しいメソッドと、Windows コモンコントロールをサポートする追加のクラスとメソッドが用意されています。 アプリケーションをビルドするときは、次のセクションで説明されているコンパイルと移行の要件に従う必要があります。

## <a name="compilation-requirements"></a>コンパイルの要件

### <a name="supported-versions"></a>サポートされているバージョン

MFC は、すべてのバージョンのコモンコントロールをサポートしています。 Windows コモンコントロールバージョンの詳細については、「[コモンコントロールバージョン](/windows/win32/controls/common-control-versions)」を参照してください。

### <a name="supported-character-sets"></a>サポートされている文字セット

Windows コモンコントロールは、ANSI 文字セットではなく、Unicode 文字セットのみをサポートしています。 コマンドラインでアプリケーションをビルドする場合は、次の2つの定義 (/D) コンパイラオプションを使用して、基になる文字セットとして Unicode を指定します。

```
/D_UNICODE /DUNICODE
```

Visual Studio 統合開発環境 (IDE: integrated development environment) でアプリケーションをビルドする場合は、プロジェクトプロパティの **[全般**] ノードで、[**文字セット**] プロパティの [ **Unicode 文字セット**] オプションを指定します。

## <a name="migration-requirements"></a>移行の要件

Visual Studio IDE を使用して、Windows コモンコントロールを使用する新しい MFC アプリケーションをビルドする場合、IDE は自動的に適切なマニフェストを宣言します。 ただし、既存の MFC アプリケーションを Visual Studio 2005 以前のバージョンから移行し、コモンコントロールを使用する場合、IDE はアプリケーションをアップグレードするためのマニフェスト情報を自動的に提供しません。 代わりに、プリコンパイル済みヘッダーファイルに次のソースコードを手動で挿入する必要があります。

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

[MFC の一般的なトピック](general-mfc-topics.md)<br/>
[階層図](hierarchy-chart.md)<br/>
[非推奨の ANSI API](deprecated-ansi-apis.md)
