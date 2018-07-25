---
title: マニフェスト リソース |Microsoft ドキュメント
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
ms.openlocfilehash: d8df7bf266bae25bd6b898012a6bad10a3d10f81
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882915"
---
# <a name="manifest-resources"></a>マニフェスト リソース
マニフェスト リソースは、アプリケーションで使用される依存関係を記述する XML ファイルです。 たとえば Visual Studio では、MFC ウィザードで生成されたマニフェスト ファイルで、アプリケーションがバージョン 5.0 と 6.0 のどちらの Windows コモン コントロール DLL を使用するかを定義します。  
  
```  
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
  
 Windows XP または Windows Vista アプリケーションのマニフェスト リソースは、アプリケーションで最新バージョンの Windows コモン コントロール (上の例で示すようにバージョン 6.0) を使用することを指定するだけではなく、 [Syslink コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760706)をサポートします。  
  
 マニフェスト リソースに含まれるバージョン情報とタイプ情報を参照するには、XML ビューアーや Visual Studio の [テキスト エディター](http://msdn.microsoft.com/en-us/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)でファイルを開きます。 詳細については、 [Visual Studio テキスト エディターでマニフェスト リソースを開く方法](../windows/how-to-open-a-manifest-resource.md)に関するページを参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、  [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)をサポートします。  
  
## <a name="limitations"></a>制限事項  
 使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [コントロール](../mfc/controls-mfc.md)   
 [リソース ファイルの操作](../windows/working-with-resource-files.md)