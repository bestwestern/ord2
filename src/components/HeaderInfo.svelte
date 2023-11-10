<script>
	import {words} from './Store';
import { createClient } from "@supabase/supabase-js";
	import {onMount} from 'svelte';
	const supabaseUrl = "https://upabdmzybbgsnbonhgmc.supabase.co";
  const supabaseKey =
  "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InVwYWJkbXp5YmJnc25ib25oZ21jIiwicm9sZSI6ImFub24iLCJpYXQiOjE2ODExMjg1NTMsImV4cCI6MTk5NjcwNDU1M30.5TeDInNIPfxKeE_KG4GcUEznh4i9wbKjUek935JSq6Y";
  const supabase = createClient(
	"https://upabdmzybbgsnbonhgmc.supabase.co",
	supabaseKey
	);
	onMount(async () => {
		let { data, error } = await supabase
		.from("ord")
		.select("*")
		//.eq("id", productid);
		words.set(data);
        
	});
</script>


<h2>{"test"}</h2>