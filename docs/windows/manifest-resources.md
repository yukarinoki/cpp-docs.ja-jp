---
title: マニフェスト リソース (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
ms.openlocfilehash: 081fd12a86c31973c7856ca7b9f3fcb129e2eb81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578283"
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

バージョンを表示し、マニフェスト リソースに含まれる情報の入力には、XML ビューアーで、または Visual Studio テキスト エディターでファイルを開くことができます。 詳細については、 [Visual Studio テキスト エディターでマニフェスト リソースを開く方法](../windows/how-to-open-a-manifest-resource.md)に関するページを参照してください。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="limitations"></a>制限事項

使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)<br/>
[リソース ファイルの操作](../windows/working-with-resource-files.md)