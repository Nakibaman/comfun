(function() {
	"use strict";

	function init($) {
		$(document).ready(function () {
			userTestingCookie();
		});

		function userTestingCookie() {
			var testCookieVal = $('script[data-ssoe]').data('ssoe');
			var testOnStr = "?user-test-on";
			var testOffStr = "?user-test-off";

			var date = new Date();
			var minutes = 120;

			var u = location.href;
			var uSearch = location.search;

			if (uSearch === testOnStr) {

				if ($.cookie('SSOE') !== testCookieVal) {

					date.setTime(date.getTime() + (minutes * 60 * 1000));
					$.cookie('SSOE', testCookieVal, {path: '/', expires: date});

					location.href = u.replace(uSearch, '');
				}
			}
			else if (uSearch === testOffStr) {
				date.setTime(date.getTime() + (minutes * 60 * 1000 * -1));

				$.cookie('SSOE', null, {path: '/', expires: date});
				location.href = u.replace(uSearch, '');
			}
		}
	}

	require(['jquery', 'lib/jquery/cookie'], init);
})();
