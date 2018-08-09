---
title: バージョン情報エディター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version.F1
dev_langs:
- C++
helpviewer_keywords:
- Version Information editor, about Version Information editor
- editors, Version Information
- resource editors, Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e57e550527bc906d3c1170e410719c57a877eec
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647382"
---
# <a name="version-information-editor"></a>バージョン エディター
バージョン情報は、製造元および製品の識別情報、製品のリリース番号、著作権と商標の通知で構成されます。 バージョン情報エディターでこのデータを作成および保守できます。これはバージョン情報リソースに保管されます。 バージョン情報リソースはアプリケーションに必須ではありませんが、アプリケーションの識別情報を収集するのに便利な場所です。 バージョン情報はセットアップ API でも使用されます。  
  
 バージョン情報リソースには、1 つの上位ブロックと 1 つ以上の下位ブロックがあります。つまり、固定された情報ブロックが上部に 1 つと、バージョン情報ブロックが下部に 1 つ以上 (他の言語や文字セット用) あります。 上部のブロックには、編集可能な数字のボックスと選択可能なドロップダウン リストの両方があります。 下位ブロックには、編集可能なテキスト ボックスだけがあります。  
  
> [!NOTE]
>  Windows 標準では、VS_VERSION_INFO という名前のバージョン リソースが 1 つだけあります。  
  
 バージョン情報エディターでは、次のことができます。  
  
-   [バージョン情報リソースの文字列の編集](../windows/editing-a-string-in-a-version-information-resource.md)  
  
-   [別の言語のバージョン情報 (新しいバージョン情報ブロック) の追加](../windows/adding-version-information-for-another-language.md)  
  
-   [バージョン情報ブロックの削除](../windows/deleting-a-version-information-block.md)  
  
-   [プログラムからのバージョン情報へのアクセス](../windows/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  バージョン情報エディターの使用中は、多くの場合、右クリックするとショートカット メニューにリソース特有のコマンドが表示されます。 たとえば、ブロック ヘッダーのエントリをポイントしているときにクリックすると、ショートカット メニューに [バージョン情報ブロックの新規作成] コマンドと [バージョン情報ブロックの削除] コマンドが表示されます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)   
 [メニューとその他のリソース](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)