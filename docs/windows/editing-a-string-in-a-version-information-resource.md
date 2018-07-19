---
title: バージョン情報リソースの文字列の編集 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- version information resources
- resources [Visual Studio], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80795f912ab41809b19e77bd33f56243541d4de1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882885"
---
# <a name="editing-a-string-in-a-version-information-resource"></a>バージョン情報リソースの文字列の編集
### <a name="to-edit-a-string-in-a-version-information-resource"></a>バージョン情報リソースの文字列を編集するには  
  
1.  1 回アイテムをクリックして選択し、もう一度クリックして編集を開始します。 バージョン情報テーブルで直接、または [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で変更を加えます。 加えた変更は、両方の場所で反映されます。  
  
     **メモ** バージョン情報エディターで **FILEFLAGS** キーを編集するとき、.rc ファイルの **デバッグ**、 **プライベート ビルド**、または **特殊ビルド** プロパティは設定できません ([プロパティ] ウィンドウ)。  
  
    -   バージョン情報エディターは、 **_DEBUG** ビルド フラグに基づいて、リソース スクリプトの #ifdef で **デバッグ** プロパティを設定します。  
  
    -   **プライベート ビルド** キーの **値** がバージョン情報テーブルに設定されている場合、 **FILEFLAGS** キーに対応する **プライベート ビルド** プロパティ ([プロパティ] ウィンドウ) は **True**になります。 **値** が空の場合、プロパティは **False**になります。 同様に、 **特殊ビルド** キー (バージョン情報テーブル内) は、 **FILEFLAGS** キーの **特殊ビルド** {b&gt; &lt;b}プロパティと関連付けられます。  
  
 キーまたは値の列見出しをクリックすることにより、文字列ブロックの情報シーケンスをソートすることができます。 これらの見出しは、選択した順序に情報を自動的に再配置します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [バージョン情報 エディター](../windows/version-information-editor.md)   
 [バージョン情報 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

