---
title: マニフェスト リソース (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
- resources [C++], opening
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
ms.openlocfilehash: 2d135cb2d512313f107eef7e95ec90d7972b68b4
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850191"
---
# <a name="manifest-resources-c"></a>マニフェスト リソース (C++)

C++ デスクトップ プロジェクトでは、マニフェスト リソースは、アプリケーションが使用する依存関係を記述する XML ファイルです。 たとえば Visual Studio では、MFC ウィザードで生成されたマニフェスト ファイルで、アプリケーションがバージョン 5.0 と 6.0 のどちらの Windows コモン コントロール DLL を使用するかを定義します。

```xml
<description>Your app description here</description>
<dependency>
    <dependentAssembly>
        <assemblyIdentity
            type="win32"
            name="Microsoft.Windows.Common-Controls"
            version="6.0.0.0"
            processorArchitecture="X86"
            publicKeyToken="6595b64144ccf1df"
            language="*"
        />
    </dependentAssembly>
</dependency>
```

Windows XP または Windows Vista アプリケーションのマニフェスト リソースは、アプリケーションで最新バージョンの Windows コモン コントロール (上の例で示すようにバージョン 6.0) を使用することを指定するだけではなく、 [Syslink コントロール](/windows/desktop/Controls/syslink-overview)をサポートします。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

バージョンを表示し、マニフェスト リソースに含まれる情報の入力には、XML ビューアーで、または Visual Studio テキスト エディターでファイルを開くことができます。 マニフェスト リソースを [リソース ビュー](../windows/resource-view-window.md)から開くと、リソースはバイナリ形式で表示されます。 マニフェスト リソースの内容を見やすい形式で表示するからリソースを開く必要があります**ソリューション エクスプ ローラー**します。

## <a name="to-open-a-manifest-resource-in-the-text-editor"></a>テキスト エディターでマニフェスト リソースを開くには

1. プロジェクトを開いてで**ソリューション エクスプ ローラー**、展開、**リソース ファイル**フォルダー。

1. .manifest ファイルをダブルクリックします。

   マニフェスト リソースを開きます、**テキスト エディター**します。

## <a name="to-open-a-manifest-resource-in-another-editor"></a>別のエディターでマニフェスト リソースを開くには

1. **ソリューション エクスプ ローラー**.manifest ファイルを右クリックし、選択、**プログラムから開く.** ショートカット メニューから。

1. **プログラムから開く** ダイアログ ボックスで、使用し、選択するエディターを指定**オープン**します。

## <a name="limitations"></a>制限事項

使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)<br/>
[リソース ファイルの操作](../windows/working-with-resource-files.md)