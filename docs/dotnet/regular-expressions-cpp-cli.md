---
description: 詳細については、「正規表現 (C++/CLI)」を参照してください。
title: 正規表現 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- regular expressions [C++]
- .NET Framework [C++], regular expressions
- regular expressions [C++], about regular expressions
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
- substrings, simple matches
- searching, exact substring matches
- strings [C++], exact substring matching
- regular expressions [C++], simple matching
- IsMatch method
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
- regular expressions [C++], rearranging data
- data [C++], rearranging
- search and replace
- Replace method
- regular expressions [C++], search and replace
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 838bab49-0dbc-4089-a604-ef146269ef5a
ms.openlocfilehash: 429a121ec7acad46437a344b089f5c6a1ce4243b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245812"
---
# <a name="regular-expressions-ccli"></a>正規表現 (C++/CLI)

.NET Framework の正規表現クラスを使用したさまざまな文字列操作を示します。

次のトピックでは、.NET Framework <xref:System.Text.RegularExpressions> 名前空間 (およびメソッド) を使用して、 <xref:System.String.Split%2A?displayProperty=fullName> 文字列の検索、解析、および変更を行う方法について説明します。

## <a name="parse-strings-using-regular-expressions"></a><a name="parse_regex"></a> 正規表現を使用して文字列を解析する

<xref:System.Text.RegularExpressions.Regex> 名前空間の <xref:System.Text.RegularExpressions?displayProperty=fullName> クラスを使用して単純な文字列を解析する方法を次のコード例に示します。 複数のワード デリニエイタの型を含む文字列が構成されます。 次に、<xref:System.Text.RegularExpressions.Regex> クラスを <xref:System.Text.RegularExpressions.Match> クラスと共に使用して文字列が解析されます。 さらに、センテンス内の各単語を個別に表示します。

### <a name="example"></a>例

```cpp
// regex_parse.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main( )
{
   int words = 0;
   String^ pattern = "[a-zA-Z]*";
   Console::WriteLine( "pattern : '{0}'", pattern );
   Regex^ regex = gcnew Regex( pattern );

   String^ line = "one\ttwo three:four,five six  seven";
   Console::WriteLine( "text : '{0}'", line );
   for( Match^ match = regex->Match( line );
        match->Success; match = match->NextMatch( ) )
   {
      if( match->Value->Length > 0 )
      {
         words++;
         Console::WriteLine( "{0}", match->Value );
      }
   }
   Console::WriteLine( "Number of Words : {0}", words );

   return 0;
}
```

## <a name="parse-strings-using-the-split-method"></a><a name="parse_split"></a> Split メソッドを使用して文字列を解析する

<xref:System.String.Split%2A?displayProperty=fullName> メソッドを使用して、文字列から各単語を抽出する方法を次のコード例に示します。 デリニエイタ リストを指定して <xref:System.String.Split%2A> を呼び出すと、複数の型のワード デリニエイタを含む文字列が構成され、解析されます。 さらに、センテンス内の各単語を個別に表示します。

### <a name="example"></a>例

```cpp
// regex_split.cpp
// compile with: /clr
using namespace System;

int main()
{
   String^ delimStr = " ,.:\t";
   Console::WriteLine( "delimiter : '{0}'", delimStr );
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ words;
   String^ line = "one\ttwo three:four,five six seven";

   Console::WriteLine( "text : '{0}'", line );
   words = line->Split( delimiter );
   Console::WriteLine( "Number of Words : {0}", words->Length );
   for (int word=0; word<words->Length; word++)
      Console::WriteLine( "{0}", words[word] );

   return 0;
}
```

## <a name="use-regular-expressions-for-simple-matching"></a><a name="regex_simple"></a> 単純な照合に正規表現を使用する

次のコード例では、正規表現を使用して、部分文字列の完全一致を検索します。 この検索は、 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 入力として2つの文字列を受け取る静的メソッドによって実行されます。 1つ目は検索する文字列で、2番目は検索対象のパターンです。

### <a name="example"></a>例

```cpp
// regex_simple.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
   array<String^>^ sentence =
   {
      "cow over the moon",
      "Betsy the Cow",
      "cowering in the corner",
      "no match here"
   };

   String^ matchStr = "cow";
   for (int i=0; i<sentence->Length; i++)
   {
      Console::Write( "{0,24}", sentence[i] );
      if ( Regex::IsMatch( sentence[i], matchStr,
                     RegexOptions::IgnoreCase ) )
         Console::WriteLine("  (match for '{0}' found)", matchStr);
      else
         Console::WriteLine("");
   }
   return 0;
}
```

## <a name="use-regular-expressions-to-extract-data-fields"></a><a name="regex_extract"></a> 正規表現を使用してデータフィールドを抽出する

次のコード例は、正規表現を使用して、書式設定された文字列からデータを抽出する方法を示しています。 次のコード例では、クラスを使用して、 <xref:System.Text.RegularExpressions.Regex> 電子メールアドレスに対応するパターンを指定しています。 このパターンには、各電子メールアドレスのユーザーとホスト名の部分を取得するために使用できるフィールド識別子が含まれています。 クラスは、 <xref:System.Text.RegularExpressions.Match> 実際のパターンマッチングを実行するために使用されます。 指定された電子メールアドレスが有効な場合は、ユーザー名とホスト名が抽出されて表示されます。

### <a name="example"></a>例

```cpp
// Regex_extract.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
    array<String^>^ address=
    {
        "jay@southridgevideo.com",
        "barry@adatum.com",
        "treyresearch.net",
        "karen@proseware.com"
    };

    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");

    for (int i=0; i<address->Length; i++)
    {
        Match^ m = emailregex->Match( address[i] );
        Console::Write("\n{0,25}", address[i]);

        if ( m->Success )
        {
            Console::Write("   User='{0}'",
            m->Groups["user"]->Value);
            Console::Write("   Host='{0}'",
            m->Groups["host"]->Value);
        }
        else
            Console::Write("   (invalid email address)");
        }

    Console::WriteLine("");
    return 0;
}
```

## <a name="use-regular-expressions-to-rearrange-data"></a><a name="regex_rearrange"></a> 正規表現を使用してデータを再配置する

次のコード例では、.NET Framework 正規表現のサポートを使用して、データを再配置または再フォーマットする方法を示します。 次のコード例では、クラスとクラスを使用して、 <xref:System.Text.RegularExpressions.Regex> <xref:System.Text.RegularExpressions.Match> 文字列から姓と名を抽出し、これらの name 要素を逆順に表示します。

クラスは、 <xref:System.Text.RegularExpressions.Regex> データの現在の形式を記述する正規表現を作成するために使用されます。 2つの名前はコンマで区切られていると見なされ、コンマの周りに任意の大きさの空白文字を使用できます。 <xref:System.Text.RegularExpressions.Match>次に、メソッドを使用して各文字列を分析します。 成功した場合、最初と最後の名前がオブジェクトから取得さ <xref:System.Text.RegularExpressions.Match> れて表示されます。

### <a name="example"></a>例

```cpp
// regex_reorder.cpp
// compile with: /clr
#using <System.dll>
using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ name =
   {
      "Abolrous, Sam",
      "Berg,Matt",
      "Berry , Jo",
      "www.contoso.com"
   };

   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");

   for ( int i=0; i < name->Length; i++ )
   {
      Console::Write( "{0,-20}", name[i] );
      Match^ m = reg->Match( name[i] );
      if ( m->Success )
      {
         String^ first = m->Groups["first"]->Value;
         String^ last = m->Groups["last"]->Value;
         Console::WriteLine("{0} {1}", first, last);
      }
      else
         Console::WriteLine("(invalid)");
   }
   return 0;
}
```

## <a name="use-regular-expressions-to-search-and-replace"></a><a name="regex_search"></a> 正規表現を使用して検索と置換を行う

次のコード例は、正規表現クラスを <xref:System.Text.RegularExpressions.Regex> 使用して検索と置換を実行する方法を示しています。 これは、メソッドを使用して行い <xref:System.Text.RegularExpressions.Regex.Replace%2A> ます。 使用されるバージョンは、入力として2つの文字列 (変更される文字列) と、オブジェクトに指定されたパターンに一致するセクション (存在する場合) の代わりに挿入される文字列を受け取ります。 <xref:System.Text.RegularExpressions.Regex>

このコードは、文字列内のすべての数字をアンダースコア (_) に置き換え、それを空の文字列に置き換えて、実質的に削除します。 1つの手順で同じ効果を実現できますが、ここでは2つの手順を使用します。

### <a name="example"></a>例

```cpp
// regex_replace.cpp
// compile with: /clr
#using <System.dll>
using namespace System::Text::RegularExpressions;
using namespace System;

int main()
{
   String^ before = "The q43uick bro254wn f0ox ju4mped";
   Console::WriteLine("original  : {0}", before);

   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");
   String^ after = digitRegex->Replace(before, "_");
   Console::WriteLine("1st regex : {0}", after);

   Regex^ underbarRegex = gcnew Regex("_");
   String^ after2 = underbarRegex->Replace(after, "");
   Console::WriteLine("2nd regex : {0}", after2);

   return 0;
}
```

## <a name="use-regular-expressions-to-validate-data-formatting"></a><a name="regex_validate"></a> 正規表現を使用してデータの書式設定を検証する

次のコード例は、正規表現を使用して文字列の書式を検証する方法を示しています。 次のコード例では、文字列に有効な電話番号が含まれている必要があります。 次のコード例では、文字列 "\d {3} -\d {3} -\d" を使用して、 {4} 各フィールドが有効な電話番号を表すことを示しています。 文字列内の "d" は数字を示し、各 "d" の後の引数は、存在する必要がある桁数を示します。 この場合、数字はダッシュで区切る必要があります。

### <a name="example"></a>例

```cpp
// regex_validate.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ number =
   {
      "123-456-7890",
      "444-234-22450",
      "690-203-6578",
      "146-893-232",
      "146-839-2322",
      "4007-295-1111",
      "407-295-1111",
      "407-2-5555",
   };

   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";

   for ( int i = 0; i < number->Length; i++ )
   {
      Console::Write( "{0,14}", number[i] );

      if ( Regex::IsMatch( number[i], regStr ) )
         Console::WriteLine(" - valid");
      else
         Console::WriteLine(" - invalid");
   }
   return 0;
}
```

## <a name="related-sections"></a>関連項目

[.NET Framework 正規表現](/dotnet/standard/base-types/regular-expressions)

## <a name="see-also"></a>関連項目

[C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
