---
description: 詳細情報:/clr でビルドされた COM オブジェクトを使用する場合の CLR シャットダウンでの例外の回避
title: -Clr を使用して構築された COM オブジェクトによってスローされた例外の回避
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
ms.openlocfilehash: 899f7905aafcf1bff92e37ee70253e74759b3f57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282615"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>/clr で構築された COM オブジェクト使用時における CLR シャットダウンの例外の回避

共通言語ランタイム (CLR) がシャットダウンモードになると、ネイティブ関数は CLR サービスへのアクセスが制限されます。 **/Clr** でコンパイルされた COM オブジェクトに対して Release を呼び出すと、clr はネイティブコードに遷移してからマネージコードに遷移し、IUnknown:: Release 呼び出し (マネージコードで定義されている) を処理します。 CLR は、シャットダウンモードであるため、マネージコードへのコールバックを防止します。

これを解決するには、Release メソッドから呼び出されたデストラクターにネイティブコードのみが含まれていることを確認します。

## <a name="see-also"></a>関連項目

[混合 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
