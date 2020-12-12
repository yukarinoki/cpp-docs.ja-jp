---
description: '詳細情報: カスタマイズによるセキュリティへの影響'
title: カスタマイズによるセキュリティへの影響
ms.date: 11/04/2016
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
ms.openlocfilehash: 64a1029dd3486e3cd653f5e692aa1a14ba6f82b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217758"
---
# <a name="security-implications-of-customization"></a>カスタマイズによるセキュリティへの影響

このトピックでは、MFC で発生する可能性のあるセキュリティ上の弱点について説明します。

## <a name="potential-security-weakness"></a>潜在的なセキュリティ上の弱点

MFC では、ボタンやアイコンなど、アプリケーションのユーザーインターフェイスの外観をカスタマイズできます。 MFC では、ユーザーがシェルコマンドを実行できるようにするユーザー定義ツールもサポートされています。 アプリケーションのカスタマイズされた設定はレジストリのユーザープロファイルに保存されるため、セキュリティの脆弱性が発生します。 レジストリにアクセスできるすべてのユーザーは、これらの設定を編集して、アプリケーションの外観や動作を変更できます。 たとえば、コンピューターの管理者は、ユーザーのアプリケーションが任意のプログラムを (ネットワーク共有からも) 実行するようにして、ユーザーの権限を借用することができます。

## <a name="workarounds"></a>回避策

レジストリの脆弱性を閉じるには、次の3つの方法のいずれかをお勧めします。

- そこに格納されているデータを暗号化する

- レジストリではなく、セキュリティで保護されたファイルにデータを格納します。

   これらの最初の2つの方法のいずれかを実行するには、 [Csettingsstore クラス](../mfc/reference/csettingsstore-class.md) からクラスを派生させ、そのメソッドをオーバーライドして、暗号化またはストレージをレジストリの外部に実装します。

- アプリケーションでカスタマイズを無効にすることもできます。

## <a name="see-also"></a>関連項目

[MFC のカスタマイズ](../mfc/customization-for-mfc.md)
