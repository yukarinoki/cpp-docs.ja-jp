---
title: CLR 統合 (C + + CX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50b455bd3b6fd4a96c3181b60904cb7a3250e866
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="clr-integration-ccx"></a>CLR 統合 (C++/CX)
一部の Windows ランタイム型では、特別な処理を受信 C + + CX と共通言語ランタイム (CLR) に基づく言語です。 この記事では、1 つの言語のいくつかの型から別の言語へのマップの仕組みについて説明します。 たとえば、CLR は Windows.Foundation.IVector を System.Collections.IList へ、Windows.Foundation.IMap を System.Collections.IDictionary へ、というようにマップします。 同様に、C + + CX が platform::delegate や platform::string などの型を特別にマップします。  
  
## <a name="mapping-the-windows-runtime-to-ccx"></a>Windows ランタイムをマッピングする C + + CX  
 ときに C + + CX が Windows メタデータ (.winmd) ファイルを読み取り、コンパイラは一般的な Windows ランタイム名前空間と型を自動的にマップすると C + +/CX 名前空間と型。 たとえば、数値の Windows ランタイム型`UInt32`に自動的にマップされて`default::uint32`です。  
  
 C + + CX マップを他のいくつかの Windows ランタイム型、**プラットフォーム**名前空間。 たとえば、 **windows::foundation**読み取り専用の Unicode テキスト文字列を表す、HSTRING ハンドルは、C + にマップされて + CX`Platform::String`クラスです。 Windows ランタイム操作では、エラーの hresult 値を返します、する場合は、C + マッピング + CX`Platform::Exception`です。 詳細については、「 [Built-in Types](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f)」を参照してください。  
  
 C + + CX も、型の機能を強化するために Windows ランタイム名前空間内の特定の種類をマップします。 これらの型、C + + CX ヘルパー コンス トラクターとは C++ に固有であり、型の標準 .winmd ファイルでは使用できませんメソッドを提供します。  
  
 新しいコンストラクターとヘルパー メソッドをサポートしている値構造体を次の一覧に示します。 構造体の初期化リストを使用するコードを既に作成済みの場合、新たに追加されたコンストラクターを使用するように変更してください。  
  
 **Windows::Foundation**  
  
-   ポイント  
  
-   Rect  
  
-   サイズ  
  
 **Windows::UI**  
  
-   色  
  
 **Windows::UI::Xaml**  
  
-   CornerRadius  
  
-   存続期間  
  
-   GridLength  
  
-   太さ  
  
 **Windows::UI::Xaml::Interop**  
  
1.  TypeName  
  
 **Windows::UI::Xaml::Media**  
  
-   [マトリックス]  
  
 **Windows::UI::Xaml::Media::Animation**  
  
-   KeyTime  
  
-   RepeatBehavior  
  
 **Windows::UI::Xaml::Media::Media3D**  
  
-   Matrix3D  
  
## <a name="mapping-the-clr-to-ccx"></a>CLR をマッピングする C + + CX  
 Visual C または c# コンパイラーが .winmd ファイルを読み込む場合に自動的にマップのメタデータ ファイルで特定の種類に適切な C + + CX または CLR 型。 CLR、IVector でなど\<T > インターフェイスが IList にマップされて\<T > です。 C + + CX、IVector\<T > インターフェイスは別の型にマップされていません。  
  
 IReference\<T >、Windows ランタイムでは、null を許容するマップ\<T > を .NET でします。  
  
## <a name="see-also"></a>関連項目  
 [その他の言語と相互運用](../cppcx/interoperating-with-other-languages-c-cx.md)