---
title: バイナリ エディター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, Binary
- resources [Visual Studio], editing
- resource editors, Binary editor
- Binary editor
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aa381c42f03bcc77575464af8f8c53ca83e0af81
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650067"
---
# <a name="binary-editor"></a>バイナリ エディター
> [!WARNING]
>  **バイナリ エディター** Express エディションでは使用できません。  
  
 バイナリ エディターを使うと、16 進形式または ASCII 形式を使用してバイナリ レベルでリソースを編集できます。 また、 [[検索] コマンド](/visualstudio/ide/reference/find-command) を使うと、ASCII 文字列や 16 進表現のバイト列を検索できます。 使用する必要があります、**バイナリ**カスタム リソースや、Visual Studio 環境でサポートされていないリソースの種類のエディターを表示またはマイナー必要がある場合にのみ変更します。  
  
 開くには、**バイナリ エディター**、最初に選択**ファイル** > **新規** > **ファイル**メイン メニューで、次のように選択します、。ファイルを編集し、横にドロップダウン矢印をクリックする、**オープン**ボタンをクリックし、選択**プログラムから開く** > **バイナリ エディター**します。  
  
> [!CAUTION]
>  ダイアログ ボックス、イメージ、メニューなどのリソースをバイナリ エディターで編集することは危険です。 編集方法が正しくないと、リソースを破損し、本来のエディターで読み取ることができなくなる場合があります。  
  
> [!TIP]
>  使用しているときに、**バイナリ**多くの場合、エディターを右クリック リソース固有のコマンドのショートカット メニューを表示します。 使用できるコマンドは、ポインターの位置によって異なります。 たとえばをポイントした状態をクリックする、**バイナリ**16 進値が選択されているエディター、ショートカット メニューを示しています、**切り取り**、**コピー**と**貼り付け**コマンド。  
  
 **バイナリ**エディターができます。  
  
-   [バイナリ編集するリソースを開く](../windows/opening-a-resource-for-binary-editing.md)  
  
-   [バイナリ データを編集する](../windows/editing-binary-data.md)  
  
-   [バイナリ データを検索する](../windows/finding-binary-data.md)  
  
-   [新しいカスタム リソースまたはデータ リソースを作成する](../windows/creating-a-new-custom-or-data-resource.md)  
  
## <a name="managed-resources"></a>マネージド リソース  
 使用することができます、[イメージ エディター](../windows/image-editor-for-icons.md)と**バイナリ**マネージ プロジェクトのエディターでのリソース ファイルを操作します。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)