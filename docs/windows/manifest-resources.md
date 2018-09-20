---
title: マニフェスト リソース (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2da93d1baaf95799c7ef68d6cc854d554fbe6c47
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429566"
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

Windows XP または Windows Vista アプリケーションでは、マニフェスト リソースだけでなくことを指定、アプリケーションを使用して、最新バージョンの Windows コモン コントロール (v6.0、上記のよう) もサポートしています、 [Syslink コントロール](/windows/desktop/Controls/syslink-overview)します。

バージョンを表示し、マニフェスト リソースに含まれる情報の入力には、XML ビューアーで、または Visual Studio テキスト エディターでファイルを開くことができます。 詳細については、 [Visual Studio テキスト エディターでマニフェスト リソースを開く方法](../windows/how-to-open-a-manifest-resource.md)に関するページを参照してください。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="limitations"></a>制限事項

使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)<br/>
[リソース ファイルの操作](../windows/working-with-resource-files.md)