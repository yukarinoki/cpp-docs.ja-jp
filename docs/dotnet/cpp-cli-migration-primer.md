---
title: C + +/CLI 移行ガイド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++/CLI Version 2
- upgrading Visual C++ applications, Managed Extensions for C++ to Visual C++ 2005 syntax
- migration [C++], C++/CLI Version 2
- Managed Extensions for C++, upgrading syntax
- C++/CLI Version 2, managed extensions
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: add55156b23dd2f9eb746f032d8406bad3b9db56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ccli-migration-primer"></a>C++/CLI 移行ガイド
これは、Visual c、c++ マネージ拡張から、Visual C プログラムを移行するためのガイドです。 
  
 C++/CLI は ISO-C++ 標準言語に対する動的コンポーネント プログラミング パラダイムを拡張します。 新しい言語では、マネージ拡張を強化するさまざまな改良が施されました。 このセクションでは、このようなマッピングが存在し、マッピングが存在しないこれらのコンストラクトを伴う Visual c マネージ C++ 言語の機能拡張の列挙とのマッピングを提供します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [変更の概略 (C++/CLI)](../dotnet/outline-of-changes-cpp-cli.md)  
 変更を 5 つのカテゴリに分類してわかりやすくまとめた、クイック リファレンスです。  
  
 [言語キーワード (C++/CLI)](../dotnet/language-keywords-cpp-cli.md)  
 言語キーワードの変更 (二重のアンダースコアの廃止やコンテキスト キーワードとスペース区切りキーワードの導入など) について説明します。  
  
 [マネージ型 (C + + CL)](../dotnet/managed-types-cpp-cl.md)  
 宣言の共通型システム (CTS) - の構文の変更について見てクラス、配列 (パラメーター配列を含む)、列挙型、およびなどの宣言に変更を含めます。  
  
 [クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 スカラー プロパティ、インデックス プロパティ、演算子、デリゲート、イベントなどのクラス メンバーに関連する変更について説明します。  
  
 [値型とその動作 (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 値型、および内部ポインターと固定ポインターの新しいファミリについて説明します。 また、暗黙的なボックス化の導入、ボックス化された値型の不変性、値クラス内の既定のコンストラクターに対するサポートの廃止など、重要なセマンティクスの変更についても解説します。  
  
 [言語の変更の概要 (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)  
 キャスト表記のサポート、リテラル文字列の動作などのセマンティクスの変更、および ISO-C++ と C++/CLI とのセマンティクスの相違について詳しく紹介します。  
  
## <a name="see-also"></a>関連項目  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)   
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)