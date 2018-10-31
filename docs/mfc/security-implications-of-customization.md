---
title: カスタマイズのセキュリティの影響 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2035e665bd7d8cba502c3516498934f32c2b3dd0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080846"
---
# <a name="security-implications-of-customization"></a>カスタマイズによるセキュリティへの影響

このトピックでは、MFC での潜在的なセキュリティ脆弱性について説明します。

## <a name="potential-security-weakness"></a>潜在的なセキュリティの脆弱性

MFC で、ユーザーは、ボタンとアイコンの外観など、アプリケーション ユーザー インターフェイスの外観をカスタマイズします。 MFC には、シェル コマンドを実行できるユーザー定義のツールもサポートしています。 アプリケーションのカスタマイズした設定はレジストリ内のユーザー プロファイルに保存されるため、セキュリティの脆弱性が発生します。 これらの設定を編集し、アプリケーションの外観や動作を変更、レジストリにアクセスできるユーザーはだれでもできます。 など、コンピューターの管理者では、(ネットワーク共有) からでも任意のプログラムを実行するユーザーのアプリケーションを発生させることによってユーザーを偽装する可能性があります。

## <a name="workarounds"></a>問題回避

レジストリの脆弱性を終了するこれら 3 つの方法のいずれかをお勧めします。

- 保管されているデータを暗号化します。

- レジストリではなく、セキュリティで保護されたファイルにデータを格納します。

   これらの最初の 2 つの方法のいずれかを行うためには、派生クラスを[CSettingsStore クラス](../mfc/reference/csettingsstore-class.md)し、暗号化またはレジストリ以外で記憶域を実装するメソッドをオーバーライドします。

- また、アプリケーションでカスタマイズを無効にします。

## <a name="see-also"></a>関連項目

[MFC のカスタマイズ](../mfc/customization-for-mfc.md)

