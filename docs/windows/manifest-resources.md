---
title: マニフェスト リソース |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources
- resources [Visual Studio], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e1520cd301fa46fb4d9521fd6d4180ebd3710f67
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218251"
---
# <a name="manifest-resources"></a>マニフェスト リソース

マニフェスト リソースは、アプリケーションで使用される依存関係を記述する XML ファイルです。 たとえば Visual Studio では、MFC ウィザードで生成されたマニフェスト ファイルで、アプリケーションがバージョン 5.0 と 6.0 のどちらの Windows コモン コントロール DLL を使用するかを定義します。

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

バージョンを表示し、マニフェスト リソースに含まれる情報を入力して、XML ビューアーで、または Visual Studio で、ファイルを開くことができます[テキスト エディター](https://msdn.microsoft.com/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)します。 詳細については、 [Visual Studio テキスト エディターでマニフェスト リソースを開く方法](../windows/how-to-open-a-manifest-resource.md)に関するページを参照してください。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください[チュートリアル: Using Resources for Localization with ASP.NET](https://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="limitations"></a>制限事項

使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)  
[リソース ファイルの操作](../windows/working-with-resource-files.md)