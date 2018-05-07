---
title: Clr で構築された COM オブジェクトによってスローされた例外の回避 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0efd2af7eb4bf8a70bff983d627f802f1976c6ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>/clr で構築された COM オブジェクト使用時における CLR シャットダウンの例外の回避
共通言語ランタイム (CLR) がシャット ダウン モードになると、ネイティブ関数には CLR サービスへのアクセスが制限されます。 COM オブジェクトをコンパイルしたに対して Release を呼び出すしようとするとき **/clr**、ネイティブ コードに遷移する CLR および iunknown::release 呼び出し (これは、マネージ コードで定義されている) に対応するマネージ コードに遷移の戻さです。 CLR では、シャット ダウン モードであるために、マネージ コードへのコールバックができなくなります。  
  
 これを解決するには、リリースのメソッドから呼び出すデストラクターがネイティブ コードのみを含めることを確認します。  
  
## <a name="see-also"></a>関連項目  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)