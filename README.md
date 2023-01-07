# ShowBuddy
Ever find yourself bored, not knowing what TV show to watch? Well, there's no need to fear; Show Buddy is here. With this program, you'll get a curated, personalized set of recommendations based on your preferred streaming platform and favorite genres. What are you waiting for? Let's get you watching TV!

```
# Program Introduction & Initial User Information Capture
print("Hello! Welcome to the Show Buddy App. Your best friend when you don't know what TV show to watch Let's curate your personalized show recommendations. First, we'd like to get to know you. What is your name?")

name = input()

print("Nice to meet you " + name + ". Now, please let us know your preferred streaming platform. (Netflix, Hulu, HBO Max) CASE SENSITIVE")
streaming_platform = input()

print("Awesome! Looks like you've chosen " + streaming_platform + ". Now, please select your favorite genre. (action, comedy, horror, reality) CASE SENSITIVE")

genre = input()

# User Information
user_information = [name, streaming_platform, genre]
streaming_platforms = ["Netflix", "Hulu", "HBO Max"]


# Function Returning Streaming Platform Index
def get_platform_index(platform):
    platform_index = streaming_platforms.index(platform)
    return platform_index

# Function Returning Platform Index For User
def get_user_platform(user):
    user_platform = user[1]
    user_platform_index = get_platform_index(user_platform)
    return user_platform_index

# Genres for loop
genres_list = []
for genres in streaming_platforms:
    genres_list.append([])

# Function Adding show at specific streaming platform index depending their Genres 
def add_show(streaming_platform, genre):
    platform_index = get_platform_index(streaming_platform)
    show_for_genre = genres_list[platform_index].append(genre)
    return

# Adding Data; i.e. Shows from each platform for each genre
add_show("Netflix", ["Kaleidoscope", ["action"]])
add_show("Netflix", ["Narcos", ["action"]])
add_show("Netflix", ["Emily In Paris", ["comedy"]])
add_show("Netflix", ["On My Block", ["comedy"]])
add_show("Netflix", ["All Of Us Are Dead", ["horror"]])
add_show("Netflix", ["The Cursed", ["horror"]])
add_show("Netflix", ["The Ultimatum", ["reality"]])
add_show("Netflix", ["Nailed It", ["reality"]])
add_show("Hulu", ["Attack On Titan", ["action"]])
add_show("Hulu", ["My Hero Academia", ["action"]])
add_show("Hulu", ["Modern Family", ["comedy"]])
add_show("Hulu", ["How I Met Your Mother", ["comedy"]])
add_show("Hulu", ["American Horror Story", ["horror"]])
add_show("Hulu", ["The Purge", ["horror"]])
add_show("Hulu", ["MasterChef", ["reality"]])
add_show("Hulu", ["Shark Tank", ["reality"]])
add_show("HBO Max", ["Barry", ["action"]])
add_show("HBO Max", ["Game Of Thrones", ["action"]])
add_show("HBO Max", ["Chowder", ["comedy"]])
add_show("HBO Max", ["Friends", ["comedy"]])
add_show("HBO Max", ["30 Coins", ["horror"]])
add_show("HBO Max", ["The Baby", ["horror"]])
add_show("HBO Max", ["Fixer Upper", ["reality"]])
add_show("HBO Max", ["Hard Knocks", ["reality"]])

# Function Matching Shows to Streaming Platforms
def find_shows(streaming_platform, genre):
        platform_index = get_platform_index(streaming_platform)
        shows_in_platform = genres_list[platform_index]

        shows_matching_genre = []

        for show in shows_in_platform:
            possible_show = show
            show_tags = show[1]

            for gen in genre:
                if gen in show_tags:
                    shows_matching_genre.append(possible_show[0])
        return shows_matching_genre

# Function Connecting User to Recommended Shows
def get_shows_user(user):
    user_platform = user[1]
    user_genres = user[2]
    user_shows = find_shows(user_platform, [user_genres])
    
    recommendation_output = print("Loading... Please wait. results will be generated momentarily. Hi " + user[0] + ", the Show Buddy apps thinks you'll like the following shows on " + user[1] + ": ")
    for i in range(len(user_shows)):
        if user_shows[-1] == user_shows[i]:
            print(user_shows[i] + ".")
        else:
            print(user_shows[i] + ".")
    return "Thank you for using Show Buddy. I hope to see you the next time you're bored and looking for new TV shows to watch! "

user_recommended_shows = get_shows_user(user_information)
print(user_recommended_shows)
```
