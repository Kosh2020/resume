  // detecting current page language 
  function getCurrentPageLang()
  {
    var full = window.location.host;
    //window.location.host is subdomain.domain.tld
    var parts = full.split('.');
    var sub = parts[0];
    if(sub == "www" || sub == "products")
    {
    	sub = "en";
    }
    return sub;
  }

  // detecting if current page is a product page
  function isProductPage(parts)
  {
    if(parts[0].toLowerCase() == "products" || parts[1].toLowerCase() == "products")
    {
    	return true;
    }
    else
    {
      return false;
    }
  }
  
  // detecting if current page is a blog page
  function isBlogPage(parts)
  {
    if(parts[0].toLowerCase() == "blog" || parts[1].toLowerCase() == "blog")
    {
    	return true;
    }
    else
    {
      return false;
    }
  }
  
  function switchLanguage(lang)
  {    
    // checking if language selection is different from the current page language
    if(lang != getCurrentPageLang())
    {
      // creating an anchor tag to get the parts of the URL
      var anchor = document.createElement('a');
      anchor.href = window.location.href;

      // getting parts of the host name
      // where host name is subdomain.domain.tld
      var parts = anchor.host.split('.');

      // lang could be 'en', 'zh', 'ja' & 'ru'
      // if lang is 'en' the subdomain is 'www'
      var subdomain = lang == "en"? "www": lang;

      // checking if current page is a product page
      if(isProductPage(parts))
      {
      	if (lang == "en")
        {
          // redirecting to English product page
          window.location = "https://products.aspose.com" + anchor.pathname.replace(/\/\s*$/,'') + anchor.hash;
        }
        else
        {
          // redirecting to other language product page
          window.location = "https://" + lang + ".products.aspose.com" + anchor.pathname.replace(/\/\s*$/,'') + anchor.hash;
        }
      }
      else if(isBlogPage(parts))
      {
      	if(lang == "en")
        {
        	window.location = "https://blog.aspose.com";
        }
        else
        {
            // redirecting to other language blog page
            window.location = "https://" + lang + ".blog.aspose.com";
        }
      }
      else
      {
        // redirecting to site home if URL is not of product or blog page
        window.location = "https://" + subdomain + ".aspose.com";
      }
    }
 
  }

  
  $( document ).ready(function() 
  {
      // remove the default flag - remove classes
      $('#menuSelectedFlag').removeAttr('class');
      // delete the inner text of span
      $('#menuSelectedLanguage').html('English');

	  // set the country flag, based on the current URL/subdomain
      // detect the subdomain, set the classes and text accordingly
      var detectedLang = getCurrentPageLang().toLowerCase();
      if (detectedLang == "ja")
      {
        // set class/flag
        $('#menuSelectedFlag').addClass('lang-ico ja-ico');
        // set Text
        $('#menuSelectedLanguage').html('日本語');
      }
    else if(detectedLang == "zh")
      {
         // set class/flag
        $('#menuSelectedFlag').addClass('lang-ico zh-ico');
        // set Text
        $('#menuSelectedLanguage').html('中文');
        
        // edited 09-Feb-2018
        // change the Sign-in menu for Chinese header
        $('#lblMenuSignInExistingUser').html('登陆');
        $('#lblMenuSignInNewUser').html('注册');
        $('#lblMenuAccountSettings span').text('设置');
        $('#lblMenuMyOrdersQuotes span').text('我的订单&报价');
        $('#lblMenuSignOut span').text('退出');
      }
    else if(detectedLang == "ru")
      {
         // set class/flag
        $('#menuSelectedFlag').addClass('lang-ico ru-ico');
        // set Text
        $('#menuSelectedLanguage').html('РУССКИЙ');
        
        // edited 25-Jan-2018
        // change the Sign-in menu for Russian header
        $('#lblMenuSignInExistingUser').html('Вход');
        $('#lblMenuSignInNewUser').html('Регистрация');
        $('#lblMenuAccountSettings span').text('Настройки аккаунта');
        $('#lblMenuMyOrdersQuotes span').text('Мои заказы и квоты');
        $('#lblMenuSignOut span').text('Выход');
      }
     else // Default in any case is English
      {
         // set class/flag
        $('#menuSelectedFlag').addClass('lang-ico us-ico');
        // set Text
        $('#menuSelectedLanguage').html('English');
      }
  });