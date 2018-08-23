---
title: プログラム内からバージョン情報へのアクセス |Microsoft Docs
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
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db32214543278023cdce91654c86e53568fffb00
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606923"
---
# <a name="accessing-version-information-from-within-your-program"></a>プログラムからのバージョン情報へのアクセス

### <a name="to-access-version-information-from-within-your-program"></a>プログラム内からバージョン情報にアクセスするには

1. プログラム内からバージョン情報にアクセスする場合を使用して、 [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa)関数と[VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea)関数。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[バージョン エディター](../windows/version-information-editor.md)  
[バージョン情報 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)